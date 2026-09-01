# Kanwei He — GitHub Pages academic website

A maintainable, English-first academic website for GitHub Pages. It uses **Jekyll**, which GitHub Pages builds natively, so shared layouts and automatic publication/blog indexes work without a JavaScript framework.

## 1. Directory structure

```text
.
├── index.md                         # Home (root index is required by GitHub Pages)
├── _config.yml
├── _data/
│   ├── profile.yml                  # Edit personal information here
│   └── i18n/
│       └── en.yml                   # English UI strings
├── _includes/                       # Shared header/footer/cards
├── _layouts/                        # Shared page templates
├── assets/
│   ├── css/main.css                 # One global stylesheet
│   ├── js/main.js
│   ├── files/Kanwei_He_CV.pdf
│   └── images/profile/
├── publications/
│   ├── index.md                     # Auto-generated list
│   ├── taros-2026/index.md          # One publication = one folder
│   ├── numerosityvlm-eccv-2026/index.md
│   └── demandomt/index.md
└── blogs/
    ├── index.md                     # Auto-generated list
    └── corolab-research-experience/
        ├── index.md                 # One blog = one folder
        └── pictures/                # Images only for this blog
```

## 2. First things to edit

Open `_data/profile.yml` and update:

- `google_scholar`
- `github` if needed
- `email`
- `location`
- wording of the 2027 PhD notice

Replace the portrait placeholder as described in `assets/images/profile/README.md`.

Also update `_config.yml`:

```yml
url: "https://YOUR_GITHUB_USERNAME.github.io"
```

## 3. Add a new publication

Copy an existing publication folder, for example:

```text
publications/taros-2026/
```

to:

```text
publications/my-new-paper/
```

Then edit only `publications/my-new-paper/index.md`.

Required front matter:

```yml
---
layout: publication
nav: publications
lang: en
content_type: publication
order: 4
year: 2027
title: "Paper title"
authors: "Author A, Kanwei He, Author B"
venue: "Conference / Journal"
status: "Accepted"
summary: "One-sentence summary."
paper_url: "https://..."
code_url: "https://..."
---
```

The Publications page automatically discovers it. No index HTML needs to be edited.

## 4. Add a new blog

Copy:

```text
blogs/corolab-research-experience/
```

to a new folder, for example:

```text
blogs/icra-2027/
```

Keep the structure:

```text
blogs/icra-2027/
├── index.md
└── pictures/
    ├── cover.jpg
    ├── 01.jpg
    └── 02.jpg
```

Edit the metadata in `index.md`, then write the blog in Markdown. Images can be embedded with relative paths:

```md
![Robot demo](pictures/01.jpg)
```

The Blogs page automatically discovers the post.

## 5. Add Chinese later

The site is already prepared for a second language:

1. Create `_data/i18n/zh.yml` based on `en.yml`.
2. Create a `/zh/` folder for Chinese pages.
3. Set `lang: zh` in their front matter.
4. Reuse the same layouts, CSS, publications/assets where appropriate.

This keeps English and Chinese content separated while sharing the visual system.

## 6. Deploy to GitHub Pages

For a user site, create the public repository:

```text
YOUR_GITHUB_USERNAME.github.io
```

Upload the **contents of this folder** to the repository root. In GitHub:

**Settings → Pages → Build and deployment → Deploy from a branch → main / root**

GitHub Pages will run Jekyll automatically.

## 7. Design principles

- English-first academic homepage
- Minimal, spacious, research-focused layout
- No external CSS/JS dependencies
- One source of truth for profile information
- One folder per publication
- One folder + `pictures/` per blog
- Shared header/footer/layouts
- Responsive mobile layout
- Light/dark theme
- Future Chinese version supported without redesigning the site

### Volleyball video
The Liverpool volleyball clip is encoded as H.264/AAC with `faststart` for broad browser compatibility. It is intentionally displayed as a 9:16 portrait clip rather than stretched into a landscape frame.
