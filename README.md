# Start &amp; Scale Your Newsletter — Waitlist Landing Page

A single-page waitlist landing page for the **5-Day Sprint**, converted from the
Claude Design component `Waitlist.dc.html` into a self-contained, deployable page.

## Files

- `index.html` — the landing page (all CSS/JS inline, no build step)
- `assets/roadmap.png` — the poster/roadmap artwork shown on the right

## Running locally

Open `index.html` directly in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Swapping the poster image

The right-hand artwork lives at `assets/roadmap.png`. Replace that file with the
final image (same path/name) and the page picks it up automatically. The image is
displayed with `object-fit: contain` and a soft left-edge mask, so any aspect ratio
works.

## Wiring up the form

The email form currently shows a client-side success state on submit. To capture
signups, point it at your email provider inside the `<script>` block in
`index.html` (see the `TODO` / `fetch('/api/waitlist', …)` comment) — e.g. a Kit
form endpoint or your own API route.

## Design variants

The original design system component supported several variants (accent color,
`Highlight` / `Knockout` / `Underline` headline styles, and `Panel` / `Full Bleed`
/ `Ghost` image presence). This page ships the default: yellow-green accent
(`#E9EF3A`), highlighted headline, and a contained poster panel. Adjust the CSS
`:root` variables and classes to change them.
