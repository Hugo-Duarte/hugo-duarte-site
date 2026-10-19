# Hugo Duarte — personal website

A small, responsive, theme-free Hugo site for a backend-focused software developer. No npm, JavaScript framework, database, analytics, cookies or third-party fonts. The source is ready for your own GitHub repository.

## Before publishing

Edit `hugo.toml`:

- Set `baseURL` to your domain, including `https://` and a trailing `/`.
- Confirm the GitHub profile URL.
- Add your email and LinkedIn URL. Empty fields are hidden automatically; currently GitHub is the only contact link.
- To enable the CV button, put your public CV at `static/files/hugo-duarte-cv.pdf` and set `cv = 'files/hugo-duarte-cv.pdf'`. Review the CV for personal information before publishing it.

All page copy is in `layouts/index.html`. Styles are in `static/css/main.css`. Content is deliberately selective: no unverified employment dates, invented results or unfinished project showcase. The work description is high level, without internal system architecture or client information. Review the wording before making it public.

## Preview locally

Install Hugo (standard edition is sufficient): https://gohugo.io/installation/

From this folder:

```sh
hugo server -D
```

Visit http://localhost:1313/. For a production build run `hugo --gc --minify`; the output goes to `public/`. This project was prepared for Hugo 0.168.0.

## Put it on GitHub Pages

1. Create a GitHub repository, preferably `Hugo-Duarte.github.io` for your account's main website (or any repository name for a project site).
2. Extract this archive. Upload **the contents of `hugo-duarte-site`**, including `.github/workflows/hugo.yaml`, to the repository root. Do not upload the ZIP itself. Using Git avoids file pickers skipping the `.github` folder.
3. Use `main` as the repository's default branch. In **Settings → Pages → Build and deployment**, select **GitHub Actions** as the source.
4. Push a change or run **Build and deploy Hugo** manually from the Actions tab. GitHub builds and deploys it automatically; the workflow uses the Pages base URL, so project subpaths work too.
5. Open the deployment URL shown by the successful workflow.

If you prefer Git from this folder, after creating an empty repository:

```sh
git init -b main
git add .
git commit -m "Add personal Hugo website"
git remote add origin https://github.com/Hugo-Duarte/YOUR-REPOSITORY.git
git push -u origin main
```

Replace `YOUR-REPOSITORY` with your actual repository name. Generated `public/` output is intentionally ignored.

## Connect your domain

1. In the repository's **Settings → Pages**, enter your domain under **Custom domain** and save. Verify domain ownership if GitHub requests it.
2. At your domain provider, configure DNS using GitHub's current instructions below. For a subdomain such as `www`, this normally means a CNAME to `Hugo-Duarte.github.io` (without a repository path). Apex/root domains require the DNS records specified by GitHub.
3. Set `baseURL` in `hugo.toml` to the chosen domain and push. Re-run the workflow after adding the custom domain so Pages supplies the new base URL.
4. Wait for DNS and GitHub's certificate provisioning, then enable **Enforce HTTPS** in Pages settings.

Do not guess DNS addresses or use a registrar's URL forwarding feature instead of hosting DNS. Choose the root or `www` as your primary domain and follow GitHub's instructions for the other if needed.

Official references:
- https://gohugo.io/host-and-deploy/deploy-to-github-pages/
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## Accessibility and maintenance

Semantic headings and navigation, skip link, visible keyboard focus, responsive layouts, reduced-motion support and no JavaScript dependency. Optional links render only when configured. This is a one-page site with a custom 404 and generated sitemap. Add projects when they are ready to show; there are no placeholder project links to maintain.
