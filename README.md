# UC Physician Salary Databases (site)

Static, self-contained search pages for UC HCOMP salary datasets (2010-2025). The repo root is the
UCLA database; `/ucsf/` and `/ucsd/` hold the same page/pipeline for UCSF and UC San Diego.

## Files
- `index.html` - the page itself (search box, year/department filters, sortable table, pagination)
- `data.json` - the dataset (38,113 records), dictionary-encoded to keep it small
- `.nojekyll` - tells GitHub Pages not to run Jekyll processing on this folder

## Deploying on GitHub Pages
1. Create a public GitHub repo.
2. Upload these files (`index.html`, `data.json`, `.nojekyll`) to the repo root via the web UI (drag and drop).
3. Repo Settings -> Pages -> Source: "Deploy from a branch" -> Branch: `main`, folder: `/ (root)` -> Save.
4. Wait a minute or two, then your page is live at `https://<username>.github.io/<repo>/`.

## Embedding in Blogger
In the Blogger post editor, switch to "HTML view" and paste:

```html
<iframe src="https://<username>.github.io/<repo>/" style="width:100%; height:800px; border:none;"></iframe>
```

## Updating the data later
Regenerate `data.json` (see `build_site_data.py` in the main project folder) and re-upload it to the
repo through GitHub's web UI - the live page updates automatically within a minute or so. No changes
to `index.html` are needed unless the data schema changes.
