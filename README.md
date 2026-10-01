# Denise Van Burgh — Luxury Real Estate, Ras Al Khaimah

Static site: one `index.html` (CSS + JS inline) and an `images/` folder. No build step, no dependencies.
Only external request: Google Fonts (Cormorant Garamond + Jost), with serif/sans fallbacks.

## Structure

```
index.html
images/
  hero/hero-1..5.jpg          hero slideshow (35s CSS loop, respects reduced motion)
  listings/<key>-<n>.jpg      card galleries (6 per listing, 5 per project)
  denise-van-burgh.jpg        portrait
  og-image.jpg                1200x630 link-preview image
```

## Deploy (any static host)

- **Netlify:** drag the folder onto app.netlify.com/drop
- **Cloudflare Pages / Vercel:** push to a repo, framework preset "None", output dir `/`
- **GitHub Pages:** push to a repo, Settings → Pages → deploy from branch

Then add the custom domain in the host's dashboard and point DNS at it (HTTPS is automatic on all three).

## After the domain is live

1. Change `og:image` in `<head>` to an absolute URL (`https://<domain>/images/og-image.jpg`) so WhatsApp/LinkedIn previews show the photo.
2. Replace the **sample testimonial** (search for `SAMPLE TESTIMONIAL` in index.html).

## Editing content

- **Listings & projects:** the `LISTINGS` and `PROJECTS` arrays at the top of the `<script>`.
  Each listing's `key` maps to `images/listings/<key>-1.jpg … <key>-<photos>.jpg`.
  `kind`, `community` and `aed` drive the hero search; `type` drives the filter tabs.
- **Contact numbers:** search for `971562000973` and `denise@islandproperties.ae`.

## Enquiries

The form builds a pre-filled WhatsApp message (or email) and opens it — nothing is stored server-side.
Recommended before launch: also POST submissions to a form backend or CRM (Formspree, Netlify Forms,
or a small endpoint) so leads are logged even if the visitor never presses Send in WhatsApp.

## Image credits

Listing photos and renders come from Denise's Property Finder listings (Island Properties FZ-LLC).
Confirm with her that she/the brokerage is happy for them to appear on the site.
