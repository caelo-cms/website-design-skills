# Screenshots at 390 and 1440 px

Tested with Playwright and an installed Google Chrome. It takes whole-page screenshots at both widths and reports horizontal overflow.

Note: headless Chrome's `--window-size=390,…` produces a viewport of at least about 500 px, so pages look fine when they are not. Playwright's `fullPage: true` (and the CLI's `--full-page`) has been seen repeating the top of the page further down. The script below avoids both: it sets the viewport to the page height and takes a normal screenshot.

## Setup (once, outside the project folder)

```
mkdir -p ~/.website-design-tools && cd ~/.website-design-tools
npm init -y && npm install playwright-core
```

Without Google Chrome installed: `npm install playwright && npx playwright install chromium`, then use `require('playwright')` and remove `channel: 'chrome'`.

## shot.js

```js
const { chromium } = require('playwright-core');
(async () => {
  const [,, url, base] = process.argv;          // url: file:///… or http://…; base: output path without width
  const b = await chromium.launch({ channel: 'chrome' });
  for (const w of [390, 1440]) {
    const p = await b.newPage({ viewport: { width: w, height: 900 } });
    await p.goto(url); await p.waitForTimeout(300);
    const { sw, sh } = await p.evaluate(() => ({
      sw: document.documentElement.scrollWidth, sh: document.documentElement.scrollHeight }));
    if (sw > w) console.log(`OVERFLOW ${w}: scrollWidth ${sw}`);
    await p.setViewportSize({ width: w, height: Math.min(sh, 16000) });
    await p.waitForTimeout(150);
    await p.screenshot({ path: `${base}-${w}.png` });
  }
  await b.close();
})();
```

Usage:

```
node ~/.website-design-tools/shot.js file:///path/to/04-structure/wireframes/r1/start.html review/screens/04-start-r1
```

Then look at both images. An `OVERFLOW` line means the page scrolls sideways at that width.

## References from other websites (step 5)

For moodboard references: one screenshot of the first screen at 1440 × 900, with cookie and newsletter dialogs accepted or removed. Save as `ref.js` next to `shot.js`:

```js
const { chromium } = require('playwright-core');
(async () => {
  const [,, url, out] = process.argv;                 // out: references/07-example.png
  const b = await chromium.launch({ channel: 'chrome' });
  const p = await b.newPage({ viewport: { width: 1440, height: 900 }, locale: 'en-US' });
  try { await p.goto(url, { waitUntil: 'domcontentloaded', timeout: 30000 }); }
  catch (e) { console.log(`FAILED ${url}: ${e.message.split('\n')[0]}`); await b.close(); process.exit(1); }
  await p.waitForTimeout(2500);
  // Accept or close cookie and newsletter dialogs, then remove what is still covering the page.
  for (const t of ['Accept all', 'Accept', 'Allow all', 'Agree', 'I agree', 'OK', 'Got it',
                   'Alle akzeptieren', 'Akzeptieren', 'Zustimmen', 'Einverstanden', 'Close', 'Schließen']) {
    const btn = p.getByRole('button', { name: t, exact: true }).first();
    if (await btn.isVisible().catch(() => false)) { await btn.click().catch(() => {}); await p.waitForTimeout(500); break; }
  }
  await p.evaluate(() => {
    for (const el of document.querySelectorAll('body *')) {
      const s = getComputedStyle(el);
      if ((s.position === 'fixed' || s.position === 'sticky') && +s.zIndex > 100 &&
          el.offsetHeight > innerHeight * 0.25) el.remove();
    }
    document.documentElement.style.overflow = 'auto'; document.body.style.overflow = 'auto';
  });
  await p.waitForTimeout(300);
  const text = (await p.evaluate(() => document.body.innerText)).slice(0, 400).toLowerCase();
  if (/verify you are human|security verification|just a moment|access denied|captcha/.test(text)) {
    console.log(`BLOCKED ${url}: bot check, no screenshot. Ask for a screenshot or pick another reference.`);
    await b.close(); process.exit(2);
  }
  await p.screenshot({ path: out });
  await b.close();
})();
```

Usage: `node ~/.website-design-tools/ref.js https://example.com 05-moodboard/references/07-example.png`

Expect some sites to fail: bot checks (Cloudflare), dead domains, dialogs the script cannot close. The script then prints `FAILED` or `BLOCKED` and saves nothing. Do not spend time on them: ask the person for a screenshot or pick another reference. Look at every captured image before using it; remove anything still covering the page and any personal data.
