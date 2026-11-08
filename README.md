# Best Bloom — Coffee Bean Tracker Framework Skill

A complete, reusable skill that builds **Best Bloom**, an all-in-one coffee companion app: track every bean you own and its freshness, get a daily "brew this first" call with the recipe to match, learn 18 real brew methods, browse a living catalogue of drippers, and keep up with new beans and coffee news.

Tagline: *Your beans, at their peak.*

## What the app does

- **Overview** — Brew First hero (which bean to brew today), Up Next queue, live counts, mood picks (Fruity / Fresh / Classy Unique / Normal-Cold Brew)
- **Beans** — photo inventory with per-bean freshness stages (Resting → Brew Now → Peak → Drink Soon → Cold Brew → Past Prime), weights, tasting-note families and storage guidance
- **Brew** — an adjustable Brew Studio (Drip 1:15, Cold Brew 1:10, Ice Drip 1:10, Cold Brew with Milk 1:8), a library of **18 brew methods** with real formulas (Kasuya 4:6 with its sweeter/brighter dial, osmotic flow, Hoffmann, Rao, Switch hybrids and more), and a photo catalogue of **34 drippers** in a 3-in-a-row grid with a personal shelf ("My Shelf") that bean recommendations map to first
- **Explore** — new beans worth buying, refreshed about every 15 days
- **News** — Singapore specialty coffee and global brewing news in five fixed categories, every item with its source page's preview photo, a one-line preview and a link

The registry is **alive**: a separate monthly market scan adds genuinely new drippers as they are released.

## How to use this skill

Give this folder to your AI agent (Muse or compatible) and ask it to build the app from `SKILL.md`. The skill is deliberately self-contained but **feeds no answers**: photo sourcing, news refresh and the monthly dripper scan are framed as research prompts inside the skill, which the building/running agent executes with its own research.

The app ships **empty of personal data**: no beans, no owned drippers, no saved stories. You onboard your own beans (send your agent a photo of each bag) and your own dripper shelf.

## Contents

- `SKILL.md` — the full framework: design system, the 5 tabs, data model, freshness engine, recommendation rules, photo rules, refresh and monthly-scan prompts, build and verification checklist with a parity gate
- `references/design-and-data-spec.md` — field-by-field data model and the full actions catalogue
- `references/methods-seed.md` / `methods-seed.json` — the 18 brew methods in full
- `references/drippers-seed.md` / `drippers-seed.json` — the 34-dripper registry
- `references/dripper-photo-pack.md` — the framed photo-research prompt and its acceptance criteria

## Notes

- No prices are shown anywhere in the dripper catalogue.
- Bean display photos follow a strict rule: the exact bag's own online photo if found (search roaster + bean name), otherwise your own photo, nicely cropped. Never a substitute.
- News and Explore photos come from each story's own source page (its preview image, or a screenshot-style page preview), fetched at save time.

Built with Muse.
