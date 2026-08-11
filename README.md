# Coding Fundamentals — Field Guides

Field guides for the tools every technical course assumes you already know.
Published for students at Cal State San Bernardino.

**Live site:** https://csusb-jhbc-cyber-ai-robotics.github.io/coding-fundamentals/

## The guides

| Guide | Covers |
|---|---|
| [Linux](Linux_Field_Guide.html) | The command line, filesystem, permissions, processes, systemd, scripting |
| [Git & GitHub](Git_GitHub_Field_Guide.html) | How Git thinks, branching, merging, pull requests, Actions, recovery |
| [Python Environments](Python_Environment_Field_Guide.html) | Interpreters, venv, pip, requirements files, conda and uv |
| [VS Code](VS_Code_Field_Guide.html) | Command palette, debugging, Git integration, remote development over SSH |

Companion site: **[Robotics Field Guides](https://csusb-jhbc-cyber-ai-robotics.github.io/robotics-field-guides/)**

## What these are

Each guide is a **single self-contained HTML file** — no build step, no
dependencies, no external requests. Each carries its own sidebar table of
contents, `Ctrl+K` search across every heading, per-chapter progress tracking,
light/dark themes, and copy buttons on every command block.

Because nothing loads from the network, a student can save one page and read it
offline — on a lab machine, on a plane, or on a robot with no internet.

## Editing

**Do not edit the HTML in this repo directly.** These files are generated.

The source of truth is the Workipedia vault at `~/Documents/Workipedia`:

- **Linux** and **Git & GitHub** are long-standing vault guides, edited in place.
- **Python Environments** and **VS Code** are built from content modules in
  `.workipedia/guidekit/guides/` via `node .workipedia/guidekit/build.mjs`.

To republish after any change:

```bash
cd ~/Documents/Workipedia/.workipedia/guidekit
node build.mjs        # rebuild generated guides into the vault
node publish.mjs      # copy into both site repos, rewriting cross-site links
node makeindex.mjs    # regenerate the landing pages
node checklinks.mjs ~/Projects/csusb/coding-fundamentals   # verify
```

`publish.mjs` rewrites links on the way out: references to a guide on the
companion robotics site become absolute URLs, and references to vault-only
guides that aren't published here have their links removed but their text kept.

## Hosting

GitHub Pages, served from the repository root on `main`. `.nojekyll` is present
so Jekyll doesn't process the files.
