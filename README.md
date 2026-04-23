# Deploy instructions

Replace the contents of your repository (`YuhanLiu11/YuhanLiu11.github.io`) with the three items in this folder:

1. `index.html` — the homepage
2. `images/profile.jpg` — the portrait
3. `.nojekyll` — tells GitHub Pages to serve the files directly, bypassing the old Jekyll theme

## Quick deploy (fresh start)

From a clone of your repo:

```bash
# Remove old Jekyll theme files
git rm -rf _config.yml _config.dev.yml _data _drafts _includes _layouts _pages _portfolio _posts _sass _site assets files markdown_generator talkmap talkmap.* Gemfile package.json CHANGELOG.md CONTRIBUTING.md
# (keep .git, LICENSE, README.md if you like)

# Copy the new files in
cp /path/to/index.html .
cp /path/to/.nojekyll .
mkdir -p images && cp /path/to/images/profile.jpg images/

git add -A
git commit -m "Redesign homepage as single static page"
git push
```

## Minimal deploy (keep old files intact, just shadow the homepage)

If you'd rather not delete anything yet:

```bash
cp /path/to/index.html .
cp /path/to/.nojekyll .
cp /path/to/images/profile.jpg images/profile.jpg
git add index.html .nojekyll images/profile.jpg
git commit -m "Add new homepage"
git push
```

The `.nojekyll` file makes GitHub Pages skip Jekyll, so `index.html` is served directly.

## Editing the page later

Everything lives in `index.html` — content, styles, markup. To update a publication, news item, etc., just edit the HTML directly.
