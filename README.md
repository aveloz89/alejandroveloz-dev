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

`assets/brand/` contains `logo.svg`, `logo-light.svg`, favicon assets, an Apple touch icon, and `og-image.png` for LinkedIn/WhatsApp/social previews.
