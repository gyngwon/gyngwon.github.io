# gwsong.dev — portfolio site

Static portfolio site for Analytics Engineer / Data Engineer / Data Analyst
job applications. Pure HTML/CSS, no build step, deployed via GitHub Actions
to GitHub Pages.

## Structure

```
.
├── index.html              # About / Home
├── projects.html           # Flagship project + SQL learning log
├── resume.html             # PDF viewer + download
├── assets/
│   ├── css/style.css       # Design tokens + all styling
│   ├── img/                # (optional) diagrams, screenshots
│   └── resume.pdf          # ← add your resume PDF here
└── .github/workflows/
    └── deploy.yml          # CI (HTML validation) + CD (Pages deploy)
```

## Before you push

1. Drop your actual resume PDF at `assets/resume.pdf`.
2. Replace the placeholder GitHub/LinkedIn/email links in `index.html`
   (search for `href="https://github.com/"`, `linkedin.com`, `mailto:`).
3. Fill in real project/dbt-docs/dashboard links in `projects.html`
   (currently `#` placeholders).
4. Swap the `<pre>` architecture diagram in `projects.html` for an actual
   image/SVG once the Airflow + Power BI stages are done, if you want more
   visual polish — the ASCII version works fine as-is.

## Deploy (first time)

1. Push this repo to GitHub as `<username>.github.io` (for a root domain)
   or any repo name (served at `<username>.github.io/<repo>`).
2. In the repo: **Settings → Pages → Source → GitHub Actions**.
3. Push to `main` — the `deploy.yml` workflow validates the HTML (CI),
   then publishes to Pages (CD). Check the **Actions** tab for the live URL.

Every subsequent push to `main` re-validates and re-deploys automatically —
no manual steps after the first setup.

## Local preview

No build tools needed — just open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```
