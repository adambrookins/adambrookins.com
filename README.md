# adambrookins.com

Personal landing page — static HTML/CSS, hosted on GitHub Pages.

## Deployment

### 1. Create the GitHub repo

Create a public repo named `adambrookins.com` (or any name) on GitHub.

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/adambrookins/adambrookins.com.git
git push -u origin main
```

### 2. Enable GitHub Pages

In the repo on GitHub: **Settings → Pages → Source → Deploy from branch → `main` / `/ (root)`**

### 3. Update GoDaddy DNS

Replace the current `@` A record (WebsiteBuilder Site) with these four GitHub Pages IP addresses:

| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | adambrookins.github.io |

### 4. Adding a sub-project

For each new sub-project (e.g., `project.adambrookins.com`):

1. Create a new GitHub repo for that project
2. Add a `CNAME` file containing `project.adambrookins.com`
3. Enable GitHub Pages on that repo
4. Add a CNAME DNS record in GoDaddy: `project` → `adambrookins.github.io`
5. Add a card to `index.html` on this site

### 5. Adding a project card to the landing page

In `index.html`, copy this block inside `.grid`:

```html
<a class="card" href="https://yourproject.adambrookins.com">
  <div class="card-inner">
    <h3>Project Name</h3>
    <p>Short description.</p>
  </div>
  <span class="arrow">→</span>
</a>
```
