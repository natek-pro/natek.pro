# natek.pro

The public website for NaTek, an independent applied AI and engineering consultancy.

## Local preview

The site is plain HTML and CSS with no build step or dependencies. From the repository root, run:

```sh
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).

## GitHub Pages deployment

This repository does not need a build workflow. For the first deployment:

1. Push the site files to the `main` branch.
2. In the repository's **Settings → Pages**, set **Source** to **Deploy from a branch**.
3. Select the `main` branch and the repository root (`/`), then save.
4. In **Settings → Pages → Custom domain**, enter `natek.pro` and save. The root-level `CNAME` file already contains the same domain.
5. At the DNS provider, remove any conflicting or parking records for the apex domain and add GitHub Pages' current records:

| Type | Name | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `natek-pro.github.io` |

GitHub also supports four optional IPv6 `AAAA` records. Confirm all values against [GitHub's current custom-domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) before editing DNS.

After GitHub reports a successful DNS check and provisions the certificate, enable **Enforce HTTPS**. DNS and certificate propagation can take time.
