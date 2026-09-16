# ducktype.tech

Company website for Duck Type LLC: the two apps (Yatzy Pop!, Cowboy for
Herdr), company details, and the company-wide support, privacy and terms
pages that app stores and Apple's organization enrollment look for.

Plain HTML and one stylesheet, no build step. Cloudflare Pages project
`ducktype-tech` deploys this repo on every push to `master`; other branches
get preview URLs on `<branch>.ducktype-tech.pages.dev`.

```
index.html          home: hero, apps, company details, contact
support.html        /support
privacy.html        /privacy
terms.html          /terms
404.html            served by Pages for unknown paths
_headers            security headers, font/image caching
assets/site.css     all styles
assets/fonts/       Young Serif, Hanken Grotesk, IBM Plex Mono (OFL, self-hosted)
assets/img/         app icons and screenshots (webp)
favicon.svg         the duck; favicon-48.png and apple-touch-icon.png are renders of it
og.png              1200x630 share image
```

Preview locally with anything that maps `/privacy` to `privacy.html`, or
just open the `.html` files.

## Keeping it current

- App screenshots and icons come from the app repos (`yatzy/server/public`,
  `cowboy/site/shots`, `cowboy/assets/icon`), resized to 600px wide webp.
- When Cowboy is live, replace the disabled "App Store soon" button in
  `index.html` with the real `apps.apple.com/app/id…` link and update its
  status row and the JSON-LD block.
- Mail addresses sit inside `<!--email_off-->` so Cloudflare's email
  obfuscation leaves them readable without JavaScript.
- Bump the effective date on privacy/terms when their text changes, and
  `lastmod` in `sitemap.xml`.
