# BFC Production Support

A lightweight internal knowledge base for the BFC Production team. Built to capture troubleshooting guides, standard operating procedures, manufacturer references, and system documentation in one accessible place.

---

## What It Is

A static documentation site built with [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/). Content is written in Markdown, stored in this GitHub repository, and automatically published to GitHub Pages on every push.

Live site: [https://bfcproduction.github.io/bfc-production-support](https://bfcproduction.github.io/bfc-production-support)

---

## Repository Structure

```
bfc-production-support/
├── docs/
│   ├── index.md              # Home page
│   ├── audio/                # Dante, consoles, signal flow
│   ├── video/                # Resolume, codecs, display
│   ├── lighting/             # MA3, Art-Net, fixture patching
│   ├── network/              # VLANs, switches, IP config
│   ├── workflows/            # SOPs and repeatable processes
│   └── assets/               # Images, logo, custom CSS
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions auto-deploy
└── mkdocs.yml                # Site configuration
```

---

## How It Works

1. Content is written as Markdown (`.md`) files in the `docs/` folder
2. Files are organized into category subfolders
3. Any push to the `main` branch triggers an automatic build and deploy via GitHub Actions
4. The live site updates within ~60 seconds of a push

No manual build steps required after initial setup.

---

## Adding Content

### Using Obsidian
Open the `docs/` folder as an Obsidian vault. Write and edit files normally. Push to GitHub when ready.

### Using GitHub Web Editor
Navigate to the correct folder in the repo, click **Add file → Create new file**, write in Markdown, and commit. No local setup required.

### File Naming
Use lowercase with hyphens, no spaces. Example: `dante-controller-setup.md`

For full instructions see [Creating a New Support Page](docs/workflows/creating-a-new-support-page.md).

---

## Local Development

If you want to preview the site locally before pushing:

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

---

## Deployment

Deployment is fully automated via GitHub Actions. The workflow file is located at `.github/workflows/deploy.yml`. On every push to `main` it installs dependencies, builds the site, and pushes the output to the `gh-pages` branch which GitHub Pages serves.

No manual deployment steps are needed.

---

## Notes

- Never include passwords, credentials, or sensitive access information in any page — reference the password manager instead
- Images should be stored in an `images/` subfolder within the relevant category folder
- Manufacturer documentation should be linked externally rather than copied — keeps references current
- The navigation is auto-generated from the folder structure — no changes to `mkdocs.yml` are needed when adding new pages
