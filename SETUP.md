# Deploying the catalogue to GitHub Pages

Four files in this folder: `index.html`, `items.json`, `.nojekyll` (empty — tells GitHub to skip unnecessary build processing), and this guide.

## 1. Create the repository
- github.com → New repository → name it anything (e.g. `dubai-sale`)
- **Note:** on a free GitHub account, Pages only works on a **public** repo. That means anyone who finds the repo on GitHub can see its contents (same photos/prices already visible on the live page — nothing extra is exposed — but the repo itself becomes browsable/searchable, unlike the private Claude link you had before). If that matters to you, GitHub Pro (~$4/mo) allows Pages on a private repo instead.

## 2. Upload the files
- On the repo page: "Add file" → "Upload files"
- Drag in all four files (yes, including the dot-file `.nojekyll`)
- Commit to the `main` branch

## 3. Turn on GitHub Pages
- Repo → Settings → Pages
- Source: "Deploy from a branch" → Branch: `main`, folder: `/ (root)` → Save
- GitHub gives you a live URL like `https://yourusername.github.io/dubai-sale/` within a minute or two

## 4. Create your access token (one-time)
- github.com → your profile picture → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token
- Resource owner: you · Repository access: "Only select repositories" → pick this one repo
- Permissions → Repository permissions → **Contents: Read and write** (leave everything else as "No access")
- Generate, and copy the token (starts with `github_pat_...`)

**Treat it like a password.** It's stored only in your own browser (localStorage), and it can only write to this one repo. If your laptop is ever lost, shared, or compromised, revoke it from that same Settings page and generate a fresh one.

## 5. Sign in as owner on the live site
- Open your live URL → click "Owner sign-in"
- Fill in: your GitHub username, the repo name, branch (`main`), and the token → Connect

You'll now see "Edit catalogue" on the page (only in your own browser — buyers never see this). Toggle "Sold" on any lot, edit prices/text, add or remove lots, then click "Save changes" — it pushes straight to GitHub and the public page updates within about a minute. Each save re-uploads the current photo set (~7–8 MB), so it can take a few seconds on a slow connection.

For anything bigger — new photos, a redesign, restructuring — it's still easiest to send it to me and I'll hand you an updated set of these same files to re-upload.
