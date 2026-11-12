# nathendel.com

Nat Hendel's personal website: plain HTML and CSS, no build step.

## Making updates

Open a Claude session in this folder and describe the change, for example:

- "Add my new paper to the Scientific Writing page"
- "Add a new page called Teaching"
- "Change the homepage intro to …"

Claude edits the files, shows a preview, and publishes once you approve.

To edit by hand instead, open the `.html` files in any text editor. The menu at
the top is repeated in every page, so a new page needs a link added in each one.

## Files

| File | Page |
|---|---|
| `index.html` | Home (`/`) |
| `scientific-writing-and-papers/index.html` | Scientific Writing and Papers |
| `scientific-writing-and-papers/introduction-to-dissertation/index.html` | Dissertation intro (PDF embedded from Google Drive) |
| `music-movies/index.html` | Music & Movies (YouTube embeds) |
| `home/index.html` | Redirects old `/home` links to `/` |
| `404.html` | "Page not found" page |
| `style.css` | All styling (colors, fonts, layout; includes dark mode) |
| `CNAME` | Tells GitHub Pages the site's domain |

## Previewing locally

```bash
ruby -run -e httpd . -p 8123
```

Then open http://localhost:8123.

---

## One-time setup: moving off Google Sites

### 1. Install Apple's command-line tools (gives you `git`)

```bash
xcode-select --install
```

Click **Install** in the dialog that appears. It takes a few minutes.

### 2. Put the site on GitHub Pages (free)

1. Create a GitHub account at github.com if you don't have one.
2. Create a new **public** repository, e.g. `nathendel.com`.
3. Push this folder to it (Claude can do this once git is installed; you'll sign in to GitHub when prompted).
4. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
5. Under **Custom domain**, enter `www.nathendel.com` and save.

### 3. Point the domain at GitHub (in Squarespace)

Sign in at **domains.squarespace.com** with the Google account you used for
Google Domains → `nathendel.com` → **DNS** → **DNS Settings**.

Current setup (done November 2026):

| Where | Record | Points to |
|---|---|---|
| Custom records | `www` CNAME | `nathan-hendel.github.io` |
| Squarespace Domain Forwarding | `nathendel.com` → `www.nathendel.com` | (keep as is) |

The bare domain is handled by Squarespace's forwarding rule, so no `@` A records
are needed. Don't add GitHub's `185.199.x.x` A records unless you delete the
forwarding rule first; Squarespace won't allow both.

Leave the other records alone: `_domainconnect` (Squarespace) and the
`…dv.googlehosted.com` CNAME (old Google verification) are harmless.

After DNS updates, tick **Enforce HTTPS** in **GitHub → Settings → Pages**.

### 4. Retire the Google Site

Once nathendel.com shows the new site, in Google Sites go to **Publish → Publish
settings** and remove the custom URL (or unpublish the site).

Keep the dissertation PDF in Google Drive: the dissertation page still embeds it from there.
