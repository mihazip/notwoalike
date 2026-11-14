# notwoalike

World map of ethnic, linguistic and religious fractionalization for 211 countries and territories. Live at <https://notwoalike.pages.dev>. The README has the data source and the credit.

## Layout

- `site/` is the full site. `site/index.html` holds the markup, the CSS, the fonts, the data and the app code.
- `site/vendor/` holds D3, topojson and d3-geo-projection. Do not move them or the fonts to a CDN: the site makes no third-party requests.
- `_local/` is untracked (source data and old handoff notes).

## Run and check

- There is no build step and there are no tests.
- Serve the site: `pnpm dlx serve site -l 5178`.
- Check a change in a browser. Labels show only in Compare mode (2 or 3 types active).

## Labels (`drawLabels` in `site/index.html`)

- Pass 1 gives each country a label at the minimum size. Pass 2 places the labels of the dots (tiny territories). Pass 3 increases the size of the country labels in fixed steps while there is room.
- The order is important: coverage first, then size. A dot label must not take the space of a country label.

## Deploy

- Hosting: Cloudflare Pages, project `notwoalike`, Direct Upload (not connected to git), free plan only.
- Deploy after a merge to `main`, from the main checkout: `pnpm dlx wrangler pages deploy site --project-name notwoalike --branch main`.

## Rules

- Do not change, shorten or move the credits block at the bottom of the page.
- Do not add an author name or other personal data to the page.
