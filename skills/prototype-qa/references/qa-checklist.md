# QA checklist

## Layout (390 px and 1440 px)
- [ ] No horizontal scrolling of the page; only tables or code scroll inside their own box
- [ ] No overlapping or cut-off text; long words and URLs wrap
- [ ] Spacing follows the named distances in `tokens.css`
- [ ] Images keep their aspect ratio, nothing is stretched
- [ ] Navigation works on mobile (menu opens, closes, is reachable by keyboard)
- [ ] Repeated elements (cards, list items) share edges, padding and baseline

## Accessibility (WCAG 2.2 AA basics)
- [ ] Text contrast at least 4.5:1, large text and UI components at least 3:1
- [ ] Visible focus on every interactive element, not hidden by sticky headers (2.4.11 Focus Not Obscured)
- [ ] Everything works with the keyboard alone, in a logical order
- [ ] Touch and click targets at least 24 × 24 px (2.5.8 Target Size)
- [ ] One `h1` per page, headings in order, landmarks (`header`, `nav`, `main`, `footer`)
- [ ] Every meaningful image has alt text; decorative images have empty alt
- [ ] Form fields have labels; errors are described in text, not only in colour
- [ ] Links say where they go ("Pricing for teams", not "click here")
- [ ] `prefers-reduced-motion` is respected
- [ ] Page language is set (`lang`)

## Performance
- [ ] Page weight within budget (check the transferred size)
- [ ] Images in modern formats (AVIF/WebP), sized for their slot, `loading="lazy"` below the fold
- [ ] Fonts: only the needed files, `font-display: swap`, preloaded if above the fold
- [ ] No render-blocking scripts; JavaScript only where needed
- [ ] LCP element (usually hero headline or image) loads early

## Content and SEO basics
- [ ] No lorem ipsum, no `draft` marks, no placeholder links left unmarked
- [ ] Every factual claim is listed in `claims.md` with a source
- [ ] Unique title and meta description per page
- [ ] Clean URLs as defined in `sitemap.md`

## Brand
- [ ] Nothing from `anti-defaults.md`
- [ ] Action colour only where `DESIGN.md` allows it
- [ ] Every colour, size and distance comes from a token
