# BFC Production Support

An internal knowledge base for the BFC Production team. Built to capture troubleshooting guides, standard operating procedures, manufacturer references, and system documentation in one accessible place.

Live site: [https://bfcproduction.github.io/bfc-production-support](https://bfcproduction.github.io/bfc-production-support)

---

## What It Is

A static documentation site built with [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/). Content is written in Markdown, stored in this GitHub repository, and automatically published to GitHub Pages on every push to `main`.

---

## Design & Theme

The site is styled to match the look and feel of [bethanynaz.org](https://www.bethanynaz.org):

- **Light theme** — white content area, dark text, black header and footer
- **Top navigation tabs** — Audio, Video, Lighting, Network, Workflows appear as top-bar tabs
- **Section hub pages** — each section's `index.md` is a card-grid landing page; articles are listed as cards with descriptions and links rather than dumped into the sidebar
- **Left sidebar** — only shows articles within the currently active section
- **Custom CSS** — `docs/assets/custom.css` handles all theme overrides; the MkDocs Material color scheme is `default` (light)

---

## Repository Structure

```
bfc-production-support/
├── docs/
│   ├── index.md              # Home/landing page
│   ├── audio/
│   │   ├── index.md          # Audio hub (card grid)
│   │   └── *.md              # Audio articles
│   ├── video/
│   │   ├── index.md          # Video hub (card grid)
│   │   └── *.md              # Video articles
│   ├── lighting/
│   │   ├── index.md          # Lighting hub (card grid)
│   │   └── *.md              # Lighting articles
│   ├── network/
│   │   ├── index.md          # Network hub (card grid)
│   │   └── *.md              # Network articles
│   ├── workflows/
│   │   ├── index.md          # Workflows hub (card grid)
│   │   └── *.md              # SOP and checklist articles
│   └── assets/
│       ├── custom.css        # All theme/style overrides
│       └── bfc-logo.png      # Site logo
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions auto-deploy to gh-pages
└── mkdocs.yml                # Site config — nav, theme, extensions
```

---

## Navigation Structure

The site uses an **explicit `nav:` block** in `mkdocs.yml` — this is required. Do not remove it or rely on auto-generation. Each section must follow this pattern:

```yaml
nav:
  - Home: index.md
  - SectionName:
    - section/index.md          # Hub page — no label, just the path
    - Article Title: section/article-file.md
```

The `navigation.indexes` feature makes the unlabeled `section/index.md` entry the clickable hub for that section. If you add a new article, you must add it to the `nav:` block or it won't appear in the sidebar.

---

## Adding a New Article

1. Create a `.md` file in the correct section folder (e.g., `docs/audio/my-new-page.md`)
2. Add it to the `nav:` block in `mkdocs.yml` under the correct section
3. Add a card for it in the section's `index.md` using the card grid format (see below)
4. Commit and push — the site deploys automatically

### Card Grid Format (for hub index pages)

```markdown
<div class="grid cards" markdown>

-   :material-icon-name:{ .lg .middle } **Article Title**

    ---

    Short description of what the article covers.

    [:octicons-arrow-right-24: Read more](article-file.md)

</div>
```

Browse available icons at [Material Icons](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/).

---

## How to Add Content

### Using Obsidian
Open the `docs/` folder as an Obsidian vault. Write and edit files normally. Push to GitHub when ready.

### Using GitHub Web Editor
Navigate to the correct folder in the repo, click **Add file → Create new file**, write in Markdown, and commit directly to `main`.

### File Naming
Use lowercase with hyphens, no spaces. Example: `dante-controller-setup.md`

For full instructions see [Creating a New Support Page](docs/workflows/creating-a-new-support-page.md).

---

## Local Development

**Requirements:** Python 3.x

**Install dependencies:**
```bash
pip3 install mkdocs-material mkdocs-glightbox --break-system-packages
```

**Run local server:**
```bash
mkdocs serve
```

**Preview at:** [http://127.0.0.1:8000](http://127.0.0.1:8000)

Changes to Markdown files and `custom.css` hot-reload automatically.

---

## Deployment

Fully automated via GitHub Actions (`.github/workflows/deploy.yml`). Every push to `main` triggers a build and deploys to the `gh-pages` branch. The live site updates within ~60 seconds.

No manual deployment steps needed.

---

## Notes & Conventions

- **Never** include passwords, credentials, or sensitive access information — reference the password manager instead
- Images go in an `images/` subfolder within the relevant section folder
- Link to manufacturer documentation externally rather than copying it — keeps references current
- The `nav:` block in `mkdocs.yml` must be kept in sync with the actual files in `docs/` — if a file exists but isn't in `nav:`, it won't appear in the sidebar
- The Network section currently has placeholder cards in its hub — replace them with real articles as documentation is written
