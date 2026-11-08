# Best Bloom — Design System & Data Spec

Companion to SKILL.md. Values marked **[extracted]** were read from the live app (actions/data, 7 Nov 2026). Values marked **[defined]** are framework standards set here because the exact value is not exposed through the app's actions — a rebuild is judged against the defined value.

---

## 1. Design system

### Identity
- App name: **Best Bloom** **[extracted]**
- Tagline: **"Your beans, at their peak."** **[extracted]**
- Sidebar icon subject: **a single coffee bean** **[extracted]** (the runtime picks the matching pool asset, e.g. a front-view coffee bean).
- Header logo mark: a **coffee bean inside a gold ring** (LogoMark), shown beside the wordmark in the app header **[extracted]**.
- Voice in UI copy: short, plain, warm; minimal text up front, detail behind taps; no em dashes **[extracted]**.

### Palette **[defined]**
| Token | Value | Use |
|---|---|---|
| `--bg` | `#FAF6EF` | App background — warm ivory |
| `--surface` | `#FFFDF9` | Cards — soft cream |
| `--surface-alt` | `#F3ECDF` | Tiles, chips, inset panels |
| `--ink` | `#33231A` | Body text — espresso brown |
| `--ink-strong` | `#241611` | Headlines — near-black espresso |
| `--ink-soft` | `#7A6A5C` | Secondary text, captions |
| `--gold` | `#B08A3C` | Accents, logo ring, ★ badges, Revolutionary badge |
| `--gold-bright` | `#C9A227` | Small highlights, active states |
| `--line` | `#E5DAC6` | Hairline dividers on ivory |

### Freshness stage colours **[defined]** (stage names and ordering extracted; hexes defined)
| Stage | Dot / pill colour |
|---|---|
| Resting | Grey `#8A8378` |
| Brew Now | Teal `#2F7E79` |
| Peak | Green `#3F9142` |
| Drink Soon | Amber `#D9930D` |
| Use for Cold Brew | Orange `#D96C27` |
| Past Prime | Muted brown-grey `#A79B8D` |

### Type **[defined]**
- Display / headlines: serif stack — `"Fraunces", Georgia, "Times New Roman", serif`. Big, high-contrast headlines (app name, Brew First bean name, section titles).
- Body / UI: sans stack — system sans (`-apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial`). All data, steps, chips and buttons.
- Numbers on Overview tiles: large serif numerals.
- Legibility rule (user-driven): never set body copy in the serif; serif is headlines only. Minimum body size ~14 px; primary card text ~16 px.

### Layout & interaction patterns **[extracted]**
- **Photo-first everywhere.** Cards lead with a photo; text is minimal (name, one status pill, ≤3 chips) and everything else lives behind a tap.
- **Stage pill + colour dot** on every bean card: coloured dot + stage label.
- **Weight bar** on bean cards: remaining vs total weight as a slim bar.
- **Big tap targets** (≥44 px), thumb-first mobile layout, single column on phone.
- **Tabs (5, fixed order): Overview · Beans · Brew · Explore · News.** Tab bar labels exactly these words.
- **Catalogue grid:** photo grids render **3 tiles in a row** at phone width (~110 px tiles at 390 px viewport), photo in a **4:3 box, object-cover, never distorted**; tile = photo + name (+ small maker line) + badge. Tapping a tile opens a **full-width detail panel directly below that tile's row** (content never squeezed inside the small tile), with a Close control; panel auto-scrolls into view.
- **Button-grid + expanding teach view** (Methods): a grid of buttons, each showing comparison facts (dose : water, ratio, total time); one method is selected (first method pre-selected); its full teach view expands inline below the grid.
- **Sliders** in the Brew Studio: dose (g), ratio, and method-specific splits (ice/water split for Ice Drip) adjust the recipe live; pours/steps rescale proportionally.
- **Refresh row** on Explore and News: `Last refreshed: <date, time> · refreshes about every 15 days` + a **Refresh now** button.
- Empty states are designed, not blank: see SKILL.md §Empty states.

---

## 2. Data model (field-by-field)

Types: `int` = integer, `str`, `bool`, `date` = ISO date (YYYY-MM-DD) or null, `ts` = ISO timestamp, `blob` = stored image blob URL. All tables also carry an auto `id` unless noted.

### 2.1 `beans` **[extracted]**
| Field | Type | Notes |
|---|---|---|
| name | str, required | Bean name as on the bag, e.g. "Ethiopia Guji Highlands" (values are user data — framework ships none) |
| roaster | str | Roaster name; may include channel, e.g. "Roaster (via subscription)" |
| origin | str | "Country · Region" free text |
| varietal | str | Comma list, may be empty |
| processMethod | str | Washed / Natural / Honey / Carbonic Maceration Natural / … ; empty if not printed on the bag — never guess |
| altitude | str | e.g. "1900 m"; empty if unknown |
| roastLevel | str | Light / Light-Medium / Medium / Medium-Dark / Dark (schema default "Medium" — always set explicitly) |
| roastDate | date \| null | Printed/written roast date; null if not on the bag |
| buyDate | date \| null | Purchase date; if estimated, the estimate is labelled in `notes`/`sourceNote` |
| tastingNotes | str | Comma list exactly as printed, e.g. "Tangerine, green apple, lime" |
| bestMethods | str | Suitability tags, drip first, e.g. "Drip / Pour-over, Cold Brew" |
| brewGuide | str | Researched per-bean brew guide, drip recipe first (ratio, temp, grind, pours, drawdown) |
| notes | str | Reading caveats, label translations, assumptions — anything uncertain is flagged here, never silently filled |
| sourceNote | str | Provenance: how/when captured, weight basis (e.g. scale reading including bag), which dates are estimates |
| status | enum | `sealed` (default) / `open` / `frozen` / `finished` |
| storageLocation | str | Free text, e.g. counter / cupboard / freezer |
| weightGrams | int | Current remaining weight |
| totalWeightGrams | int | Original bag size |
| photoUrl | blob | The user's own photo of the actual bag — always kept |
| displayPhotoUrl | blob | The DEFAULT display photo (web product photo or cropped own photo — see photo rule) |
| displayPhotoSourceUrl | str | Source page of the web display photo; empty when display = own photo |
| isExample | bool | True only for the labelled EXAMPLE seed bean |
| createdAt | ts | Intake timestamp |

Derived at render (never stored): freshness stage per method (drip default), days since roast, % weight remaining, running-low flag (`weightGrams < 40`), note families (mapped from tastingNotes via the 7-family taxonomy).

**Framework seed: the table starts EMPTY** (plus optionally one clearly labelled EXAMPLE bean via `seedexample`, marked `isExample: true` and labelled EXAMPLE in the UI).

### 2.2 `recipes` (user's own saved recipes) **[extracted]**
| Field | Type | Notes |
|---|---|---|
| name | str | |
| method | str | Free text method label, e.g. "Iced Drip" |
| doseGrams | int | |
| waterGrams | int | |
| iceGrams | int | 0 when not applicable |
| grind | str | |
| tempLabel | str | Free text, e.g. "Iced — sparkling water" |
| steps | str | Steps joined by newlines, one step per line |
| notes | str | |

**Framework seed: EMPTY.** The four Brew Studio presets (SKILL.md §Brew) are app constants, not rows in this table. This table backs the user's own saved recipes (add/update/delete/list) only.

### 2.3 `brew_methods` **[extracted]** — seed content: references/methods-seed.md / .json (18 records, ship in full)
Fields: `slug` (PK), `name`, `creator`, `difficulty`, `dripperSlug` (→ drippers.slug), `doseGrams` (int), `waterGrams` (int), `ratioLabel`, `tempLabel`, `grind`, `totalTime`, `flavour`, `theory`, `suits`, `steps` (array of `{at: str, to: int|null, text: str}`), `sourceUrls` (array), `verified` ("index").

### 2.4 `drippers` **[extracted, prices stripped]** — seed content: references/drippers-seed.md / .json (34 records, ship in full)
Fields: `slug` (PK), `name`, `maker`, `geometry`, `materials`, `sizes`, `filter`, `flow`, `cup`, `forgiveness` (Low / Medium / High / Very high), `strengths`, `weaknesses`, `sourceUrls` (array), `owned` (bool — **false for all records in the framework seed**), plus a bundled local `photo` asset per record (not a DB field — an app asset; see SKILL.md §Photos).
The live schema also carried `priceBand`; **the framework drops it: never store, seed or render a dripper price.**

### 2.5 `bean_brew_recs` **[extracted]** — generated per bean, never seeded with user data
| Field | Type | Notes |
|---|---|---|
| beanName | str | Key — the bean's name |
| dripperSlug | str | Researched IDEAL dripper (→ drippers.slug) |
| methodSlug | str | Method paired with the ideal dripper |
| why | str | Why the ideal pick fits (rules cited in prose) |
| alternative | str | Alternative dripper + method, free text |
| shelfDripperSlug | str | Best pick FROM THE USER'S OWNED SHELF (shelf-first mapping) |
| shelfMethodSlug | str | Method paired with the shelf pick |
| shelfWhy | str | Why the shelf pick works; when ideal ∉ shelf, names the ideal and the substitution logic |
| source | enum | `researched` (badge "Researched pick") / `generic` (badge "Generic rule") |

Framework seed: **no rows** (no beans). Rows are created at bean intake (researched where a researched pick exists, else by the generic fallback tree) and re-mapped whenever the owned shelf changes.

### 2.6 `explore_items` **[extracted]**
| Field | Type | Notes |
|---|---|---|
| name | str, required | Bean/product name |
| roaster | str | |
| seller | str | Who sells it (seller product pages only) |
| origin | str | |
| processMethod | str | |
| roastLevel | str | |
| tastingNotes | str | |
| whyLine | str | One line: why this pick |
| priceLabel | str | Bag price as listed (Explore ONLY — the no-prices rule applies to drippers, not to buyable beans) |
| sourceUrl | str, required | Seller product page; mandatory — no link, no item |
| photoUrl | blob | Page-preview photo (see photo rule) |
| foundOn | ts | Batch save timestamp — drives "Last refreshed" |

Replaced **wholesale** on each refresh save. Framework seed: empty; the Refresh now / scheduled refresh populates it.

### 2.7 `news_items` **[extracted]**
| Field | Type | Notes |
|---|---|---|
| headline | str, required | |
| summary | str | ONE-LINE preview, ~15 words max, single teaser sentence |
| sourceName | str | Publisher name |
| sourceUrl | str, required | Article link; mandatory — no link, no item |
| publishedLabel | str | Display date, e.g. "7 Nov 2026" |
| region | enum | `Singapore` / `Global` — drives the two sub-feeds |
| category | str | One of the five fixed tags: Singapore Specialty / Cafes & Events / Global Trends / Drippers & Gear / New Brew Methods. (Live-data quirk: the trends tag is stored as "Global" in the live build; the canonical tag set is the five above.) |
| highlight | bool | True = revolutionary item → gold ★ Revolutionary badge, sorts first within its feed |
| photoUrl | blob | Page-preview photo (see photo rule) |
| foundOn | ts | Batch save timestamp — drives "Last refreshed" |

Replaced **per region** on each refresh save (an empty Singapore batch never wipes the Global feed and vice versa). Framework seed: empty.

---

## 3. Actions catalogue **[extracted]**

Action names are lowercase in the live API. Classification: **Core** = framework behaviour, rebuild it · **Maintenance** = one-time repair/seed utility in the live app; rebuild only if needed for seeding · **Personal** = carries user data in the live app; the framework ships the mechanism with NO data.

| Action | Class | Purpose & key parameters |
|---|---|---|
| `listbeans` | Core | All beans, newest first, with photo URLs. |
| `addbean` | Core | Create a bean. Only `name` required; every other field defaults (see hazard below). Also attaches a dripper recommendation (researched if one exists, else generic rule). |
| `updatebean` | Core | Update a bean by `id`. **⚠ FULL-PAYLOAD RULE (see §4).** |
| `deletebean` | Core | Delete by `id`. |
| `extractfromphoto` | Core | Read a bag photo → extract roaster, name, origin, processMethod, roast level, tasting notes to pre-fill the add form. |
| `uploadphoto` | Core | Store a bag photo (base64) → returns blob key + URL. |
| `attachbagphotos` | Core (pattern) | Attach the user's own bag photos to beans. Photo-columns ONLY; idempotent; skips beans that already have a photo. |
| `applybeanphotos` | Core (pattern) | Apply the bean photo rule (web default vs cropped own photo). Photo-columns ONLY (`displayPhotoUrl`, `displayPhotoSourceUrl`). |
| `listrecipes` | Core | User's saved recipes, oldest first. |
| `addrecipe` / `updaterecipe` / `deleterecipe` | Core | CRUD for §2.2. |
| `getbrewlibrary` | Core | Returns { methods[18], drippers[34], recs[] } — powers Methods, Drippers and bean recommendations. |
| `seedbrewlibrary` | Maintenance | Idempotent upsert of the 18 methods, 34 drippers and researched recs from the research seed. In the framework: seeds methods + drippers only (no recs — no beans). |
| `listexplore` | Core | Current Explore items + `updatedOn` (last-refreshed ts). |
| `listnews` | Core | Current News items in two feeds (Singapore / Global), revolutionary first within a feed + `updatedOn`. |
| `refreshdiscover` | Core | Start a refresh: spawns the research task with the standing simple prompt (SKILL.md §Refresh). No params. |
| `savediscoveritems` | Core | Save a refresh batch: `{ explore: [...], news: [...] }` (schemas §2.6/§2.7; `sourceUrl`/`headline`/`name` required; photos as base64+mime when the research attached them). Explore replaced wholesale; News replaced per region. Save path fetches page-preview photos for any row saved without one. |
| `backfilldiscoverphotos` | Maintenance | Repair: for every stored News/Explore row with a link but no photo, fetch the page preview and store it — photo column only. |
| `seedexample` | Maintenance | Seed ONE bean clearly labelled EXAMPLE (isExample: true), showing the capture format. |
| `importcapturedbeans` | Personal | One-time import of a specific user's photographed bags. Framework: do not ship data; the mechanism = photo-first intake via `addbean`. |
| `seeddiscover` | Personal | Live app's hand-researched Explore/News seed. Framework: feeds start EMPTY and fill via refresh. |
| `seeduserrecipes` | Personal | Live app's owner recipes (an ice-drip set). Framework: `recipes` starts empty. |
| `restorebeanweights` | Maintenance | Set named beans back to verified weights (undo test logs); reopens a bean wrongly marked finished. |
| `fixexploreitems` / `retagnewsitems` / `shortennewspreviews` | Maintenance | One-time corrections in the live app (taste-rule cleanup / feed retag / one-line previews). Framework: the rules themselves are defaults in SKILL.md, so no correction pass is needed. |

---

## 4. Safety rules (non-negotiable) **[extracted]**

1. **`updatebean` resets unsupplied fields.** The action's schema gives every field a default (`roastLevel` → "Medium", `totalWeightGrams`/`weightGrams` → 250, `status` → "sealed", strings → ""). A partial update therefore WIPES data (this happened in the live app: a weight-only update blanked two beans). **RULE: every `updatebean` call carries the bean's FULL current field set**, changing only the intended fields. In-app update paths (brew logging, storage moves) must do the same.
2. **Photo changes go through photo-only actions** (`attachbagphotos` / `applybeanphotos` pattern): they touch only photo columns and verify all other fields are byte-identical afterwards.
3. **Never guess a label field.** If the bag doesn't print it (process, roast date, varietal…), store it empty/null and flag the gap in `notes`.
4. **Estimated dates are labelled as estimates** in `notes`/`sourceNote`, never presented as printed facts.
5. **No prices for drippers**, anywhere (cards, detail panels, registry). Explore bag prices (`priceLabel`) are allowed — they come from the seller's product page.
6. **Photos are bundled local assets / owned blobs**, never long-term hotlinks (dripper photos, bean display photos, News/Explore previews are all downloaded and stored).
