# Aurelia

A one-page website for Aurelia, a hand-poured candle brand. Built with plain HTML and CSS: no JavaScript, no build step, no dependencies.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole page: hero, collection, craft, burn guide, footer |
| `styles.css` | All styling and the CSS-drawn candle and jars |
| `README.md` | This file |

## Run it

Open `index.html` in any browser. The only outside request is Google Fonts (Instrument Serif and Hanken Grotesk). Offline, the page falls back to Georgia and system fonts.

## What's on the page

- **Hero:** a lit candle drawn with CSS and inline SVG. The flame flickers gently; the animation stops if the visitor has reduced motion turned on.
- **Collection:** six candles, each with its own jar colour. Hovering or tabbing to a product lights a small flame on the jar.
- **Our craft:** the four steps of making a candle.
- **Burn guide:** expandable questions built with `<details>`, so no script is needed.
- **Footer:** a mailing-list form.

## Customise

- **Colours and fonts:** edit the variables at the top of `styles.css` (`:root`).
- **Products:** each `<article class="product">` in `index.html` holds one candle. Change the name, scent notes and price, and set `--jar` (jar colour) and `--tint` (background colour) in the `style` attribute.
- **Prices:** shown in `$`. Change the symbol in the HTML if you sell in another currency.
- **Copy:** the scent names, batch size, wax temperatures and burn times are sample content. Replace them with your real details.

## Ordering and the mailing list

Without JavaScript or a server, the page cannot run a real checkout. For now:

- Each "Order" link opens an email to `hello@aurelia.example` with the candle name filled in.
- The mailing-list form sends to the same address.

Replace `hello@aurelia.example` throughout `index.html` with your own address. When you're ready for a proper shop, use a hosted service such as Shopify Buy Button, Snipcart or Stripe Payment Links, and point the "Order" links at it. A form service such as Formspree or Buttondown can handle the mailing list.

## Photos

The jars are drawn in CSS so the site works without any images. To use product photos, replace the `.jar` element inside each `.tile` with an `<img>` that has descriptive `alt` text.

## Deploy

Upload the folder to any static host: GitHub Pages, Netlify (drag and drop), Cloudflare Pages or Vercel.

## Accessibility

Includes a skip link, visible keyboard focus, semantic headings, descriptive labels on the decorative drawings, and a responsive layout down to phone width.
