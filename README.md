# edwardastill.com

Edward Astill’s personal website. Static HTML and CSS, built with Vite and Bun 1.4.0. No backend is required.

## Local development

```sh
bun install
bun run dev
```

Edit `index.html` for the profile content and `style.css` for the design. The initial copy is a holding page; replace it with your bio and verified links when ready.

```sh
bun run build
bun run preview
```

Production files are written to `dist/`. Google Fonts is used for typography, with local sans-serif fallbacks.

## GitHub Pages (recommended)

1. Create a GitHub repository and push this project to its `main` branch. GitHub Free requires a public repository for Pages.
2. In repository **Settings → Pages → Build and deployment**, select **GitHub Actions**.
3. Run the included deployment workflow (or push to `main`).
4. In **Settings → Pages**, set the custom domain to `edwardastill.com`. For an Actions deployment, configure the domain here even though `public/CNAME` is included.
5. At your domain registrar, configure the apex domain’s DNS using GitHub’s current instructions linked below; point `www` to your GitHub username’s `github.io` hostname. Remove any conflicting records for those hostnames.
6. Enable **Enforce HTTPS** when GitHub has issued the certificate.

Verify domain ownership in GitHub before pointing DNS. Hosting and DNS are not configured by creating these local files.

- [GitHub Pages custom domain setup](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Domain verification](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)

## Vercel alternative

Import the GitHub repository into Vercel with the Vite preset. Use `bun install --frozen-lockfile` as the install command, `bun run build` as the build command, and `dist` as the output directory. Add `edwardastill.com` in the project's Domains settings and follow its DNS instructions. Vercel controls its installed Bun version; the GitHub workflow explicitly pins Bun 1.4.0.

Use only one provider’s DNS configuration at a time. The GitHub deployment workflow is only needed if you choose GitHub Pages.
