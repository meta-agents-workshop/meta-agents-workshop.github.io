# Managing Agents that Manage Agents · NeurIPS 2026 Workshop

Site for the NeurIPS 2026 Workshop on Responsible Use of Meta-Agents
(Sydney, Australia, December 11-12, 2026), served via GitHub Pages at
<https://meta-agents-workshop.github.io/>.

## Structure

Plain HTML/CSS/JS static site, no build step. Each page is self-contained
with inline styles and scripts.

- `index.html`: the production page. Full-viewport hero, dark Overview +
  Speakers section, dawn gradient into light CFP/Dates/Schedule/Organizers,
  scroll-driven Sydney line-drawing finale, footer with contact info.
- `variants/`: design-exploration mockups. Published only under `/dev/`;
  excluded from the production build. Keep the content in every variant in
  sync with `index.html` so comparisons are purely visual.
- `assets/`: people photos, sponsor logos, favicons, and the social card.
- `HERO-ART-BRIEF.md`: the standing brief for the commissioned hero
  illustration (constraints, verification checklist, prompt).
- `.github/workflows/pages.yml`: the Pages deploy.

## Branches and deployment

One GitHub Actions workflow assembles the published site from two branches:

- `main` is served at the site root (production). The `variants/` folder is
  excluded from this copy.
- `dev` is served under `/dev/` as an unlinked, hidden staging copy,
  including `variants/`, for previewing changes before merging to `main`.

The workflow tolerates a missing `dev` branch; create `dev` from `main`
to enable the staging copy.

GitHub Pages must be set to build from **GitHub Actions** (repo Settings >
Pages > Source) rather than from a branch.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Content rules

- There is one canonical copy of the content (overview, CFP, dates, people):
  `index.html` on `main`. Sync it into variants; never fork the wording.
- No em-dashes in visible copy.
- Speaker bios stay within two lines at card width.

## Hero image

The hero currently uses a hand-built CSS placeholder (dusk gradient plus an
inline SVG constellation). `HERO-ART-BRIEF.md` documents the constraints for
the commissioned illustration and how to swap it in.
