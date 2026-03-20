# Andrija Ilic — Portfolio

Clean, engineering-precision portfolio site.
Built with plain HTML + CSS (no frameworks, no build step).

---

## File Structure

```
portfolio/
├── index.html              ← Home page
├── projects.html           ← Projects listing
├── experience.html         ← Experience timeline
├── techstack.html          ← Tech stack
├── style.css               ← All styles (one file)
└── assets/                 
    ├── screenshot-1.png
    ├── demo.mp4
    └── ...
```

---

## How to Run

Just open `index.html` in a browser. No server needed for local development.

For a proper local dev server (optional, recommended):
```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

---

## Personalisation Checklist

### index.html
- [ ] Replace `AI` initials placeholder with `<img class="hero-photo" src="assets/andrija.jpg" />`
- [ ] Edit the bio paragraph (`.hero-bio`)
- [ ] Update GitHub, LinkedIn, and email links in `<footer>`
- [ ] Adjust the three highlight cards to match your actual focus areas

### projects.html
- [ ] Replace placeholder cards with your real projects
- [ ] Link each card to its detail page

### experience.html
- [ ] Fill in your real roles, companies, dates, and descriptions
- [ ] Add tech tags per role

### techstack.html
- [ ] Trim / add tech pills to match your actual stack
- [ ] Mark your primary skills with the `tag-accent` badge
- [ ] Move items between "solid" and "currently exploring" as you grow

### Adding a new project or experience entry
1. Duplicate `project-template.html` → rename to e.g. `project-robot-arm.html`
2. Fill in title, description, tags, and media blocks
3. Add a matching `.card` to `projects.html` with `href` pointing to your new file

---

## Customisation Notes

All design tokens live in `style.css` under `:root {}`:

```css
--bg:      #f5f3ef   /* page background */
--accent:  #c84b2f   /* red accent — change to any colour you like */
--ink:     #1c1a17   /* primary text */
--ink-dim: #6b6660   /* secondary / muted text */
```

To change the colour scheme, update `--accent` and `--accent-dim`.
Everything else adapts automatically.

---

## Adding HTMX later

Because the site is plain HTML, dropping in HTMX is trivial:

```html
<script src="https://unpkg.com/htmx.org@2.0.0"></script>
```

You can then add `hx-get`, `hx-target`, and `hx-swap` attributes
to load project/experience partials dynamically without page reloads.
Consider extracting the nav and footer into Jinja2 `{% include %}` blocks
if you move to a Flask/FastAPI backend.
