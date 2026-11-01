# Swastha Home Made Food: Website

A 5-page website (Home, About, Gallery, Menu, Contact) built with React and Framer Motion. Orders go through WhatsApp.

## Files

```
index.html     the whole site: styles, components and content
images/        product and gallery photos
README.md      this file
```

## Run it locally

Open `index.html` in a browser. For best results, serve the folder instead:

```
npx serve .
```

or

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

An internet connection is needed. React, Framer Motion, Babel and Google Fonts load from CDNs.

## Edit the content

Everything is near the top of the `<script type="text/babel">` block in `index.html`:

| What | Where |
|---|---|
| WhatsApp number, phone, Instagram, location, Maps link | `const BIZ = { ... }` |
| Products, prices, pack sizes, categories | `const PRODUCTS = [ ... ]` |
| Gallery photos and captions | `const GALLERY = [ ... ]` |
| Customer reviews | `const REVIEWS = [ ... ]` |
| Colours | `:root { ... }` at the top of the `<style>` block |

To add a photo, put it in `images/` and use its file name in `PRODUCTS` or `GALLERY`.

## Before going live

- [ ] Confirm prices. Only the Gojju price (₹249 / 500 g) comes from the label.
- [ ] Replace the 4 sample reviews with real ones.
- [ ] Confirm the About page story and delivery details.
- [ ] Confirm the PIN code (562 123 on the real jar, 560 123 on the poster).
- [ ] Add the real Google Map. In Google Maps, choose Share, then Embed a map, and copy the `src`.
  In the `MapBox` component, replace the drawn map with:
  `<iframe src="YOUR_EMBED_SRC" width="100%" height="100%" style={{border:0}} loading="lazy" allowFullScreen></iframe>`

## Deploy for free

- **Netlify:** go to app.netlify.com/drop and drag the whole folder in.
- **Vercel / GitHub Pages:** push the folder to a repository and deploy it as a static site.

Then connect the client's domain (e.g. swasthafood.in) in the hosting settings.

## Note for production

This version compiles JSX in the browser with Babel, which is fine for a small site. For faster loading, move the code into a Vite + React project (`npm create vite@latest`) and run `npm install framer-motion`.
