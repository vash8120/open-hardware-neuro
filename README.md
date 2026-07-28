# Open-hardware tools — minimal (images + links)

A stripped-down companion site: a landing page links to three topics
(Behavior, Electrophysiology, Imaging); each topic lists its tools; each tool
page shows just its photos and a **Links** section for papers and websites.

## Put it online (new GitHub repo)

1. Create a new, empty repository on GitHub (any name).
2. Upload the CONTENTS of this folder to the repo root (so `index.html`,
   `_config.yml`, `_tools/`, `_layouts/`, and `assets/` sit at the top level —
   not inside a subfolder).
3. Open `_config.yml` and set `baseurl` to `/YOUR-REPO-NAME` (leading slash, no
   trailing slash). For a custom domain or a user site, use `baseurl: ""`.
4. Repo **Settings → Pages**: source = branch `main`, folder `/ (root)`. Save.
5. Live at `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/` within ~1 minute.

## Edit a tool page

Each tool is one file in `_tools/`. Add photos by dropping image files into the
matching `assets/img/<topic>/` folder and listing them under `images:`. Add
references under `## Links` using `- [Title](https://...)`. That's it — no other
sections.
