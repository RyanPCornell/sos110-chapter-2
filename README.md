# SOS 110 — Chapter 2 Web Slideshow

A click-through web version of the Chapter 2 ("Ethics, Economics, and Policy:
Who or What Do We Value?") slides — 30 slides.

This folder is **self-contained** — everything it needs is inside it (only
Google Fonts and the Firebase SDK come from public CDNs).

## Contents
- `index.html` — the slideshow (open this)
- `media/` — slide images
- `food-externalities/` — the embedded Food & Externalities Explorer
- `true-costs/` — the embedded True Cost Calculator
- `firebase-config.js` — Firestore config for the live class interactives
- `.nojekyll` — tells GitHub Pages to serve all files as-is

## Live interactives

Five **decision polls** (slides 5–9) and one **Tragedy of the Commons fishery
game** (slide 22) sync across every open copy through Firebase Firestore.

**Open the projected copy with `?host` appended to the URL:**

```
https://ryanpcornell.github.io/sos110-chapter-2/?host
```

Students use the plain URL (no `?host`). The host copy is the only one that can:

| Slide | Host controls |
|---|---|
| 5–9 (polls) | **Release results** (toggles to Hide) · **Reset results** |
| 22 (fishery) | Pond size + **Start the game** · **End round — harvest!** · **Next round** · **End game** |

Poll votes stay secret — students see only "your vote is locked in" — until the
host releases them. Slides 5–6 turn the water toxic if **even one** student
doesn't dispose; slides 7–9 use the **>20%** threshold.

### Keyboard
`←` / `→` navigate · `F` fullscreen · `O` slide menu

## Re-building this bundle

The deck is generated from `_deck-builder/chapter2.py` (not stored in this repo):

```bash
cd "…/Web Apps/_deck-builder"
FOOD_APP="food-externalities/index.html" \
COSTS_APP="true-costs/index.html" \
DECK_OUT="…/Web Apps/chapter-2-web/index.html" \
python3 chapter2.py
```

## Hosting on GitHub Pages

Upload the *contents* of this folder to the repo root (so `index.html` is at the
top level), then **Settings → Pages → Source: Deploy from a branch → `main` /
`(root)`**.
