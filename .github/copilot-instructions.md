# Copilot Instructions for SoftServe-Academy

## Project Overview

This is a static HTML/CSS team portfolio website built by a group of Ukrainian university students as part of a SoftServe Academy course. There is **no build system, no package manager, no server-side code, and no automated tests**. All content is plain HTML and CSS.

## Repository Structure

```
/
├── index.html                    # Main landing page (entry point)
├── css/
│   ├── styles.css                # Global styles for index.html
│   ├── aboutAllen.css            # Styles for Allen's profile page
│   └── aboutOleh.css             # Styles for Oleh's profile page
├── html/
│   └── team/
│       ├── aboutAllen.html       # Profile page for Allen (Укачукву Аллен, Kharkiv/НУРЕ)
│       ├── aboutOleh.html        # Profile page for Oleh (В. Олег, Lviv)
│       └── aboutyaroslav.html    # Profile page for Yaroslav (Співак Ярослав, Kharkiv) — note: all-lowercase, unlike other files
├── content/
│   └── images/
│       └── Allen.png             # Profile photo for Allen
├── .gitignore                    # Visual Studio / VS Code gitignore template
├── LICENSE
└── README.md
```

## Language and Encoding

- **All user-visible content is written in Ukrainian** (`lang="uk"` or `lang="ua"`).
- Files use **UTF-8** encoding. Always preserve this when editing HTML.

## Tech Stack

- **Plain HTML5** — no frameworks, no templating engines.
- **Plain CSS3** — no preprocessors (no Sass/Less). Each profile page has its own CSS file in `css/`. `aboutyaroslav.html` uses inline `<style>` instead of a separate stylesheet.
- **No JavaScript** — the site has no JS files.

## File Naming & Conventions

- HTML pages for team members live in `html/team/`.
- Each member's CSS file lives in `css/` and is named `about<Name>.css` (camelCase, first letter of name capitalized). Note: `aboutyaroslav.html` is an exception — it uses all-lowercase, deviating from the pattern of `aboutAllen.html` and `aboutOleh.html`.
- Images live in `content/images/`.
- Relative paths are used throughout (e.g., `../../css/aboutAllen.css` from inside `html/team/`).

## Known Issues / Quirks

- `index.html` uses a Windows-style backslash path for the stylesheet (`href=".\css\styles.css"`), which may not resolve correctly on non-Windows servers. Forward slashes (`./css/styles.css`) are preferred.
- The team list in `index.html` has four members (Аллен, Ярослав, Марина, Олег), but **Марина's profile page does not yet exist** in the repository.
- The `<a href="#">` links in `index.html` are placeholders — they do not yet point to the individual profile pages.
- `aboutyaroslav.html` embeds its CSS inline rather than linking to an external file, unlike the other profile pages.

## How to Preview

Open `index.html` directly in any web browser — no local server is required for basic viewing. To correctly resolve relative paths, serving from the repository root (e.g., `python3 -m http.server`) is recommended.

## No CI/CD

There are no GitHub Actions workflows, linters, or test runners configured. No build or test commands need to be run before committing. When making changes, manually open the affected HTML files in a browser to verify they render correctly.

## Adding a New Team Member

1. Create `html/team/about<Name>.html` modelled after an existing profile page.
2. Create `css/about<Name>.css` for the member's styles (or use inline styles as Yaroslav's page does).
3. Add a profile image to `content/images/` if available.
4. Update `index.html` to link the member's list item to their new page.
