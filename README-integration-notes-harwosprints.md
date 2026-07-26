# Harwosprints Blog — Integration Notes

## Files to upload
Drop these four into the same root folder as `index.html` / `store.html` — self-contained, no external CSS/JS to wire up:

- `blog.html` — index/listing page
- `blog-large-format-printing-lagos-guide.html`
- `blog-uv-direct-imaging-branded-merchandise.html`
- `blog-branded-souvenirs-nigeria.html`

## Brand color caveat
I couldn't confirm an exact brand hex from the fetched page (no CSS in the markdown, and no color-coded elements like avatar backgrounds to reverse-engineer this time). I used a signal-orange (`#FF5A1F`) on graphite (`#1B1E1F`) palette to match their "tactical/precision" copy tone, distinct from 27668grafix's gold. If Harwosprints has an actual locked-in brand color, swap the `--signal` and `--signal-deep` CSS variables at the top of each file's `<style>` block — that's the only place it's defined, so one find-and-replace per file covers it.

## One thing to add to the existing site
Add a `Blog` link to the main nav on `index.html`, `store.html`, `about.html` — right now only the new blog pages link back to the main site.

## Heads up — unrelated to this task
Their live footer currently reads "© 2024 27.668grafix. All rights reserved." on both `index.html` and `store.html` — looks like a leftover from a shared template. Worth flagging to them since it's on their live site.

## Add to sitemap.xml

```xml
<url><loc>https://www.harwosprints.ng/blog.html</loc><changefreq>weekly</changefreq></url>
<url><loc>https://www.harwosprints.ng/blog-large-format-printing-lagos-guide.html</loc><changefreq>monthly</changefreq></url>
<url><loc>https://www.harwosprints.ng/blog-uv-direct-imaging-branded-merchandise.html</loc><changefreq>monthly</changefreq></url>
<url><loc>https://www.harwosprints.ng/blog-branded-souvenirs-nigeria.html</loc><changefreq>monthly</changefreq></url>
```

If there's no sitemap/robots.txt yet, submit `blog.html` directly via Google Search Console → URL Inspection → Request Indexing.

## Adding a new post later (manual, no CMS)
Same pattern as 27668grafix: duplicate a `blog-*.html`, update the title/meta/canonical/OG/Twitter tags, the `BlogPosting` + breadcrumb JSON-LD, the `<h1>`/dek/byline, and the body. Add a new card to `blog.html`'s grid and swap out one of the "Coming soon" placeholders. Update 2–3 related-reading links on existing posts to cross-link the new one.
