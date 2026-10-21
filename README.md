# alejandroveloz.dev

Static bilingual portfolio for Alejandro Veloz.

## Important before launch

1. Configure both `alejandroveloz.dev` and `www.alejandroveloz.dev` to the same site.
2. Redirect one hostname to the other (recommended canonical: `https://alejandroveloz.dev`).
3. Enable HTTPS.
4. Verify the four resume download links.
5. Verify `usamarvin.com` and `easy-quotes.com` links.
6. If you later add LinkedIn/GitHub, add them to the header/contact section.
7. Consider adding real product screenshots to the Marvin and Easy Quotes cards once available.

## Product screenshots

The selected Marvin and Easy Quotes screenshots are included under `assets/products/`. Product cards stay secondary to the engineering story; clicking them opens an in-page case study.

## Deploy as a Static Site in Coolify

This project is intentionally plain static HTML/CSS/JavaScript. No Dockerfile and no build step are required.

Recommended Coolify setup:
- Resource type: Static Site
- Repository root: `/`
- Build command: leave empty
- Publish directory: `/` or the repository root, depending on the Coolify UI version
- Domains: `alejandroveloz.dev` and optionally `www.alejandroveloz.dev`

Recommended canonical hostname: `https://alejandroveloz.dev`, with `www` redirecting to it.

Cloudflare:
- `A @ -> <your VPS IP>` (Proxied)
- `CNAME www -> alejandroveloz.dev` (Proxied)

## Brand assets

`assets/brand/` contains `logo.svg`, `logo-light.svg`, favicon assets, an Apple touch icon, and `og-image.png` for LinkedIn/WhatsApp/social previews. `logo-light.svg` is the variant reserved for a future light mode and is not referenced anywhere yet.

## Contact modal and email delivery

The consulting CTA opens a bilingual contact form and posts via AJAX to FormSubmit, addressed to `aveloz_89@hotmail.com`. No backend or secret is embedded in the static site. The contact-section email link remains available as a fallback.

Before relying on the form in production:
1. Submit a test inquiry from the deployed domain.
2. Open the FormSubmit activation email in the recipient inbox (check junk) and confirm the destination.
3. Submit another inquiry and verify receipt and Reply-To behavior. A successful API response confirms acceptance, not inbox delivery.

The form includes required fields, length limits, a honeypot, duplicate-submit prevention and a 20-second timeout. Failed requests retain the entered text. FormSubmit processes the submitted name, email, company and message; review its service/privacy terms for your deployment. Provider availability and spam filtering affect delivery.

Documentation: https://formsubmit.co/ and https://formsubmit.co/ajax-documentation

When changing `app.js` or `styles.css`, update their `?v=` values in `index.html` using the first 12 hexadecimal characters of each file's SHA-256 digest, and regenerate the static ZIP.
