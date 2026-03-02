# AGENTS.md

## Cursor Cloud specific instructions

This is a static HTML/CSS/JS personal portfolio site ("vCard"). There are no build tools, package managers, or dependencies to install.

### Running the dev server

Any static file server works. For example:

```
python3 -m http.server 4000 --bind 0.0.0.0
```

Site will be available at `http://localhost:4000`.

### Key notes

- No build step, lint, or automated tests exist in this repository.
- All assets (CSS, JS, images) are self-contained under `assets/`.
- Blog posts are plain HTML files under `blog/`.
- Validation is done by opening the site in a browser and verifying pages render correctly.
