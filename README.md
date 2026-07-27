# Poster companion site

A small Jekyll site for your poster QR code. A landing page links to three
topics — **Behavior**, **Electrophysiology**, and **Imaging** — and each topic
lists tools. Every tool has its own page with photos, build notes, and a
"Build files coming soon" banner.

Everything is placeholder content right now. You swap in your real photos and
notes by editing simple files — no coding required.

---

## 1. Put it online (GitHub Pages)

This is already configured for the repo **vash8120/open-hardware-neuro**.

1. Upload every file in this folder into that repo, replacing the existing
   `index.html` and `README.md`. Drag-and-drop into the GitHub web UI works, or
   use git (see below).
2. In the repo: **Settings → Pages → Build and deployment**. Set **Source** to
   "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
3. Wait ~1 minute. Your site appears at
   **https://vash8120.github.io/open-hardware-neuro/** — point your QR code there.

`_config.yml` already has `baseurl: "/open-hardware-neuro"`, so links and images
resolve correctly. (Only change it if you rename the repo or add a custom domain.)

### Uploading with git
```bash
git clone https://github.com/vash8120/open-hardware-neuro.git
# copy the contents of this folder into the clone, then:
cd open-hardware-neuro
git add -A
git commit -m "Add poster site"
git push
```

## 2. Edit the basics

Open `_config.yml` and change `title`, `tagline`, and the three category
`blurb`s. That's the text on the landing page.

## 3. Add / edit a tool  ← the part you'll do most

Each tool is one file in the `_tools/` folder. To add a tool, **copy an
existing file**, rename it, and edit the block at the top:

```yaml
---
title: "Your Tool Name"
category: behavior          # behavior | electrophysiology | imaging
order: 1                    # position within the category
summary: "One line shown on the category card."
images:
  - /assets/img/behavior/my-photo-1.jpg
  - /assets/img/behavior/my-photo-2.jpg
build_status: coming_soon   # leave as-is until files are ready
---

## Overview
Write your build notes here in plain Markdown.
```

- **Photos:** drop image files into `assets/img/behavior/` (or `.../electrophysiology/`,
  `.../imaging/`) and list their paths under `images:`.
- **Build notes:** everything below the `---` is your notes. Use `##` for
  headings, `-` for bullets, `1.` for numbered steps.
- **Delete a tool:** just delete its file.

## 3b. Writing section-wise (photos between / beside your text)

Instead of the strip of photos at the top of a tool page, you can place each
photo right next to the text about it. Two steps:

1. In the tool's front matter, turn off the top gallery by adding:
   `gallery: false`
2. In the notes, drop a photo wherever you want it with this one-liner:

```
{% include fig.html img="behavior/trackball-vr-1.jpg" caption="What this shows" %}
```

- `img` is the path **under `assets/img/`** (so `behavior/…`, `electrophysiology/…`,
  or `imaging/…`). `caption` is optional.
- Add `side="right"` or `side="left"` to float the photo and let your text wrap
  beside it. Leave `side` off for a full-width photo with text above/below.
- Optional `width="360px"` sets the size of a floated photo.

Example — a photo on the right with text flowing beside it:

```
{% include fig.html img="behavior/trackball-vr-2.jpg" side="right" caption="The ball" %}

Then just write normally here. This paragraph wraps to the left of the photo.
Start a new "## Heading" whenever you want the next photo to begin a fresh row.
```

The **Trackball VR** page is already set up this way — open `_tools/trackball-vr.md`
to see the pattern, and replace the *(italic placeholder)* text with your own.
On phones, floated photos automatically stack full-width.

## 4. When build files are ready

In that tool's file, change `build_status: coming_soon` to
`build_status: available`, then optionally add:

```yaml
build_files_url: "https://github.com/USER/REPO/tree/main/files/my-tool"
build_files_note: "CAD, BOM and firmware in the linked folder."
```

The "coming soon" banner is replaced by a download button.

---

## Preview it on your own computer (optional)

You don't need this to publish — GitHub builds the site for you. But if you want
a local preview:

```bash
gem install bundler
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```
