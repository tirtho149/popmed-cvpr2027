# POPMed workshop website

Static site for **Pixels, Omics, and Patients: Efficient and Trustworthy
Multimodal Vision for Healthcare (POPMed)**, a *proposed* CVPR 2027 workshop.
**Acceptance is pending**; the site must say so until CVPR accepts the workshop.

No build step, framework, or external dependency: `index.html`, `assets/style.css`,
and images. All links are relative, so the site works under a GitHub Pages
project subpath (`https://<user>.github.io/<repo>/`).

## Preview locally

```bash
python3 -m http.server 8000   # from this folder
open http://localhost:8000
```

## Deploy

GitHub Pages serves the repository root of `main` (Settings → Pages → Deploy
from a branch → `main` / root). A `.nojekyll` file disables Jekyll processing.
Pushing to `main` redeploys within a minute or two.

## Updating content

| What | Where |
|---|---|
| Status line (change only after CVPR accepts) | `index.html`: `.status` in the hero, plus footer and `<meta>` description |
| Dates | `index.html` `#dates` table; official dates come from the CVPR call |
| Speakers | `index.html` `#speakers`; add a person only after they confirm |
| Call for papers | `index.html` `#cfp`; remove the "Provisional" notice only after acceptance |
| Organizers | `index.html` `#organizers` (initial avatars; add photos only with permission) |
| Evidence figure and numbers | regenerate with the analysis pipeline, then copy `community_interest.png` and update the four stat tiles |
| Venn figure | `figures/src/make_venn.py` in the project repo → `expertise_venn_web.svg` |
| Colours, type | `assets/style.css` (`:root` tokens) |

## Accessibility

Semantic landmarks, a skip link, visible focus rings, alt text on every figure,
tables with header cells, `prefers-reduced-motion` respected, and AA text
contrast. The mobile menu is a progressive enhancement: without JavaScript the
navigation stays visible.

## Licence

Text and figures: CC BY 4.0. Code (HTML/CSS/JS): MIT. See `LICENSE`. No CVPR,
IEEE, or CVF logos are used; this site is not endorsed by them.
