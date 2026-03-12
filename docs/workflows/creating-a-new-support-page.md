# Creating a New Support Page

This guide explains how to add a new documentation page to the BFC Production Support site.

---

## Before You Start

Every page on this site is a plain Markdown (`.md`) file stored in the `docs/` folder of the GitHub repository. When a change is pushed to GitHub the site rebuilds and publishes automatically within about 60 seconds.

---

## Prerequisites

- Access to the GitHub repo: [BFCProduction/bfc-production-support](https://github.com/BFCProduction/bfc-production-support)
- A GitHub account with access to the repo
- Basic familiarity with Markdown (see reference at the bottom of this page)

---

## Procedure

### Option A — Using Obsidian (recommended for Alan)

- [ ] Open the `bfc-production-support/docs` vault in Obsidian
- [ ] Navigate to the correct category folder (`audio`, `video`, `lighting`, `network`, or `workflows`)
- [ ] Create a new file — use lowercase with hyphens, no spaces (example: `dante-controller-setup.md`)
- [ ] Write your content using Markdown formatting (see reference below)
- [ ] If you have images, save them to the `images/` folder inside the same category folder
- [ ] Reference images in your doc like this: `![Description](images/your-image.png)`
- [ ] Push to GitHub — the site will rebuild automatically

### Option B — Using GitHub Web Editor (recommended for team members)

- [ ] Go to [github.com/BFCProduction/bfc-production-support](https://github.com/BFCProduction/bfc-production-support)
- [ ] Navigate to the correct folder under `docs/`
- [ ] Click **Add file** → **Create new file**
- [ ] Name the file using lowercase with hyphens, no spaces (example: `dante-controller-setup.md`)
- [ ] Write your content in the editor
- [ ] Click **Commit changes** with a brief description of what you added
- [ ] Site rebuilds automatically

---

## Adding the Page to the Navigation

New pages do not appear in the site navigation automatically. The `mkdocs.yml` file in the root of the repo controls the nav and must be updated manually.

- [ ] Open `mkdocs.yml` in Obsidian or the GitHub web editor
- [ ] Find the correct category section under `nav:`
- [ ] Add a new line following this format:

```yaml
  - Audio:
    - Overview: audio/index.md
    - Your New Page Title: audio/your-new-file.md
```

- [ ] Save and push — the nav will update on next deploy

---

## File Naming Convention

| Do | Don't |
|---|---|
| `dante-controller-setup.md` | `Dante Controller Setup.md` |
| `resolume-video-stuttering.md` | `Resolume Video Stuttering Fix FINAL.md` |
| `ma3-artnet-config.md` | `ma3 artnet config v2.md` |

Lowercase, hyphens only, no spaces, no version numbers in the filename.

---

## Category Guide

| Category | Use for |
|---|---|
| `audio/` | Dante, consoles, signal flow, playback audio |
| `video/` | Resolume, codecs, display, video signal |
| `lighting/` | MA3, fixture patching, networking, control |
| `network/` | Infrastructure, VLANs, switches, IP config |
| `workflows/` | SOPs, checklists, repeatable processes |

---

## Markdown Quick Reference

```markdown
# Heading 1
## Heading 2
### Heading 3

**bold text**
*italic text*

- Bullet item
- Another item

- [ ] Checkbox (unchecked)
- [x] Checkbox (checked)

[Link text](https://example.com)

![Image description](images/your-image.png)

`inline code`
```

---

## Notes

- Never include passwords or credentials in any page — reference the password manager instead
- If you are documenting a manufacturer system, link to the official docs where possible
- Keep pages focused on one topic — create a new page rather than making one page too long
