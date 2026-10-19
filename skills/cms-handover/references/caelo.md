# Handover to Caelo CMS

Caelo is an open-source CMS built for working with AI: people configure and decide, AI builds and edits. It keeps sites consistent through a theme with tokens, modules with named fields and page templates, and it never publishes on its own. Check the current documentation at https://caelo-cms.com/docs/ before starting; tool names below may change between versions.

## Connect your agent

Caelo exposes its admin as an MCP server. With "Power-MCP" your own agent (Claude Code, Codex, Cursor, …) uses Caelo's full tool catalogue directly, and Caelo makes no AI calls of its own unless you allow it, so the build runs on your own AI subscription. As Owner, open `/settings/mcp` in the Caelo admin, mint a token with scope `admin` and copy the command shown there. In Claude Code it looks like this:

```
claude mcp add caelo-admin \
  --env CAELO_ADMIN_URL=https://admin.example.com \
  --env CAELO_MCP_TOKEN=mcp_<token> \
  -- bunx --package @caelo-cms/mcp-server@latest caelo-admin-mcp
```

Details: https://caelo-cms.com/docs/mcp/. Open a session and read the site context first; it contains the site model, the tool guide and the skills that apply to the site. Follow those skills where they are more specific than this file.

## Two ways in

**A. Bring your own design.** Caelo's Site Genesis can take the prototype's HTML as the design source (a design draft with source kind `byod_html`) and derive theme, modules and templates from it. It expects one self-contained HTML file with inline CSS, so merge the prototype page and its stylesheets first; scripts are stripped. The design is already decided, so tell the agent to skip Caelo's own variant proposals. Good for a fast start; check the result module by module against the prototype afterwards.

**B. Build the system step by step.** Usually better for larger sites:
1. **Theme:** set the theme tokens from `tokens.css` (colours, fonts, spacing, radius, shadow). Caelo's theme has its own token names and roles; write a short mapping table into `handover.md` (your token → Caelo token) before setting them, and read the current theme first. Upload or acquire fonts through Caelo so they are served from the site.
2. **Modules:** one module per building block from `components.html`, with semantic fields (headline, text, link, image, alt text). Avoid modules that are one big HTML field.
3. **Templates and layouts:** header, footer and navigation once in the layout; one template per page type.
4. **Pages:** create pages from templates and fill the module fields with the approved copy.
5. **Redirects and SEO:** bulk-create the redirects from `sitemap.md`; fill SEO fields per page.

## Quality gate

Changes go from a shared draft to a protected staging site ("Stage"). A Stage that changes how pages look (modules, templates, layout, theme, new pages) runs Lighthouse on mobile for the homepage plus the changed pages, up to five per Stage. The target is 100 in performance, accessibility, best practices and SEO, and every finding blocks publishing until it is fixed or a person accepts it. A published page without a meta description stops the Stage. Because only five pages are measured per Stage, also run your own QA from step 9 on the other staging pages. Details: https://caelo-cms.com/docs/quality-gate/.

## Going live

Everything the agent does lands in a draft. Publishing live is always a click by a person in the Caelo admin. Approval-bound actions (themes, templates, domains, users and others) appear as approval cards there.

## After launch

Editors change content through the module fields or Caelo's built-in assistant; the theme and modules keep the design from step 7. Keep `DESIGN.md` in the project and point new AI sessions to it.
