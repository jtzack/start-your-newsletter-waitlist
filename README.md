# Start &amp; Scale Your Newsletter — Waitlist Landing Page

A single-page waitlist landing page for the **5-Day Sprint**, converted from the
Claude Design component `Waitlist.dc.html` into a self-contained, deployable page.

## Files

- `index.html` — the landing page (all CSS/JS inline, no build step)
- `assets/syn-sneak-peek.png` — the sneak-peek artwork shown on the right

## Running locally

Open `index.html` directly in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Swapping the poster image

The right-hand artwork lives at `assets/syn-sneak-peek.png`. Replace that file with the
final image (same path/name) and the page picks it up automatically. The image is
displayed with `object-fit: contain` and a soft left-edge mask, so any aspect ratio
works.

## The signup form (Kit / ConvertKit)

The email form is wired to **Kit form `9680893`**. It posts to
`https://app.kit.com/forms/9680893/subscriptions` (field `email_address`) and is
enhanced by Kit's `ck.5.js` runtime, which handles AJAX submission, validation,
and the configured redirect to the confirmation page on success. If the script
fails to load, the form falls back to a normal POST to Kit.

The form keeps the dark theme styling — Kit's default classes and injected CSS
are intentionally left out so they don't override the design. To point at a
different Kit form, update the form's `action`, `data-sv-form`, `data-uid`, and
the `redirect_url` inside `data-options` in `index.html`.

## Design variants

The original design system component supported several variants (accent color,
`Highlight` / `Knockout` / `Underline` headline styles, and `Panel` / `Full Bleed`
/ `Ghost` image presence). This page ships the default: yellow-green accent
(`#E9EF3A`), highlighted headline, and a contained poster panel. Adjust the CSS
`:root` variables and classes to change them.
