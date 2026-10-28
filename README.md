# Duszkiewicz Lab placeholder website

A self-contained static landing page for https://www.du-lab.com/.

## Files
- `index.html`: everything needed for the website, including CSS and a custom illustration. No external hosting, libraries, or assets required.
- `CNAME`: tells GitHub Pages to use `www.du-lab.com` as the custom domain.

## Publish on GitHub Pages
1. Sign in to GitHub and create a **public** repository, e.g. `du-lab-website`.
2. Use **Add file > Upload files** and upload `index.html` and `CNAME` to the top level of the repository (not inside a subfolder). Commit the changes.
3. Open the repository's **Settings > Pages**. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
4. In **Settings > Pages**, make sure **Custom domain** is `www.du-lab.com`. Save it if necessary.
5. In Namecheap **Domain List > Manage > Advanced DNS > Host Records**, add:

| Type | Host | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | YOUR_GITHUB_USERNAME.github.io |

Replace `YOUR_GITHUB_USERNAME` with your exact GitHub username, WITHOUT the repository name or `https://`. Set TTL to Automatic. Delete only conflicting `@` or `www` parking, redirect, A, or CNAME records; do not delete unrelated MX/email records. Keep your existing nameservers if using Namecheap BasicDNS/PremiumDNS/FreeDNS.
6. After DNS resolves and GitHub issues the certificate, select **Enforce HTTPS** in GitHub Pages settings.
7. Verify both https://www.du-lab.com and https://du-lab.com. The latter should redirect to the former.

DNS propagation can take up to 24 hours; HTTPS provisioning can also take some time.

## Editing
Edit `index.html` directly in GitHub or VS Code and commit to `main`. GitHub Pages republishes changes automatically.

This site uses an illustrative neural compass graphic, not experimental data. Research text and contact details should be reviewed before publication.

Sources:
- https://www.namecheap.com/support/knowledgebase/article.aspx/9645/2208/how-do-i-link-my-domain-to-github-pages/
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
