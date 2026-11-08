---
name: best_bloom_framework
description: Rebuild Best Bloom exactly — a photo-first coffee bean tracker ("Your beans, at their peak.") with 5 tabs (Overview · Beans · Brew · Explore · News), a freshness engine that says what to brew first, an 18-method brew library with a 34-dripper catalogue and shelf-first per-bean dripper recommendations, and self-refreshing Explore/News feeds. Ships with NO user data: no beans, empty dripper shelf.
---

# Best Bloom — Framework Skill

Build the Best Bloom coffee app from this skill alone. Everything needed is here or in `references/`:

- `references/methods-seed.md` / `.json` — the 18 brew methods, full seed content.
- `references/drippers-seed.md` / `.json` — the 34 drippers, full seed content (no prices, none owned).
- `references/dripper-photo-pack.md` — the framed photo-research prompt: builders execute it with their own research to obtain every dripper's verified bundled photo. The skill deliberately ships no photo sources or bytes for this; a build without this step ships placeholder tiles and is **not at parity** (see §8 rule 1).
- `references/design-and-data-spec.md` — design system, data model field-by-field, actions catalogue, safety rules.

**Data rule for the whole framework: NO personal data.** The bean list starts empty, the dripper shelf starts empty (`owned: false` on all 34), there are no saved user recipes and no pre-filled Explore/News items. Methods and drippers are framework content and ship in full.

---

## 1. Identity & design

- **Name:** Best Bloom · **Tagline:** "Your beans, at their peak."
- **Sidebar icon subject:** a single coffee bean.
- **Header:** gold-ring coffee-bean logo mark beside the wordmark.
- **Design system:** warm ivory background, espresso-brown text, gold accents; serif display type for headlines, clean sans for body; photo-first cards; big tap targets; minimal text up front, detail behind taps. Full tokens (palette, stage colours, type, layout patterns) in `references/design-and-data-spec.md` §1.
- **Default posture: drip-first.** Drip is the default brew method everywhere: default freshness clock = drip clock, bean cards lead with the drip recipe and drip rating, Brew First and mood picks recommend for drip first; espresso/cold brew/other are secondary badges.

## 2. The 5 tabs (fixed order: Overview · Beans · Brew · Explore · News)

### 2.1 Overview (default landing tab)
- **Brew First hero:** the biggest photo card on the tab — the #1 ranked bean (see §4 ranking), its display photo, name, stage pill, and a **"Brew this"** button that jumps to the Brew tab with that bean's recipe/method loaded.
- **Up Next:** the next 3 beans in the Brew First ranking, smaller photo cards.
- **Four big-number tiles:** total **bags**, total **grams** remaining, count **at peak**, count **running low** (beans under 40 g).
- **Mood tiles:** Fruity · Fresh · Classy Unique · Normal/Cold Brew (definitions §5). Tapping a mood tile jumps to the Beans tab filtered to the mood's match (best match first), with the pick explained in one line ("Picked: washed • jasmine + citrus • at peak, day 12").
- If there are no beans, Overview shows the empty state (§8) instead of hero/tiles.

### 2.2 Beans
- Photo grid of all beans (display photo leads), each card: photo, roaster + name, **stage pill + colour dot** (drip stage), weight bar (remaining vs total), ≤3 tasting-note chips.
- **Freshness stage per bean** computed from roast date + roast level (§4), shown for drip by default; bean detail shows the per-method timeline (drip / espresso / cold brew stages for the same age).
- **Alerts strip:** beans entering peak, drink-soon deadlines, cold-brew rescue candidates, running-low beans — derived from the stage engine and reminder triggers (§4.4).
- **Storage guidance section:** the hot-humid storage rules (§7) as short cards, including the "never the fridge" myth card.
- **Bean detail (tap a card):** full photos (display photo + "Your own photo of this bag"), all fields (§data spec 2.1), researched brew guide (drip first), the bean's dripper recommendation (§6) with badge, freshness timeline, display-photo source link when the display photo came from the web.
- **Add form (backup intake):** the user normally onboards by sending bag photos to the agent, who extracts fields (`extractfromphoto`) and researches the bean; the in-app form mirrors the same fields. Only name is required; unknown label fields stay blank.
- Unknown/estimated data is flagged in the UI copy (estimates labelled; gaps shown as gaps, never filled by guessing).

### 2.3 Brew
Three stacked sections:

**(a) Brew Studio — ONE adjustable recipe, four preset tabs.** Presets set the sliders; the user then adjusts dose/ratio/splits and the steps rescale live.
| Preset | Ratio | Definition |
|---|---|---|
| Drip | **1:15** | The general drip standard. Default grind/temp guidance by roast (light 94–96 °C finer · medium ~93 °C · dark 88–92 °C coarser). |
| Cold Brew | **1:10** | IMMERSION: coarse grounds steeped in cold water **12–16 hrs**, then strained. No ice split. (Cold brew ≠ ice drip — never merge them.) Dilute concentrate to taste when serving. |
| Ice Drip | **1:10** | Slow drip over ice: ice/water split slider ~**50/50**, drip rate **~1 drop per 1–2 seconds**, hours-long. Pro line: 1:10 with the 50/50 split. |
| Cold Brew with Milk | **1:8** | Immersion concentrate (steeped like Cold Brew) served with milk. |
Below the presets: the user's own saved recipes (table `recipes`, starts empty) with add/edit/delete.

**(b) Methods — button grid + expanding teach view.**
- A "Compare the methods" button grid of all 18 seeded methods; each button shows comparison facts: **dose : water, ratio, total time**.
- One method selected at a time (the first — Kasuya 4:6 — pre-selected); its **teach view expands inline below**: formula facts, theory ("how it works"), timed pour steps, flavour, suits, difficulty, source links, and a **"Brew this"** action that loads the method into a dose-rescaling guided brew flow (pours rescale proportionally to the chosen dose).
- **Kasuya 4:6 balance dial (interactive, required):** the 4:6's first 40% (120 g of 300 g, 2 pours) is a sweetness ↔ acidity dial with three stops — **Sweeter 40+80 · Balanced 60+60 · Brighter 80+40** — turning it rewires the guided pour amounts (first pour 40/60/80 g, second pour the remainder to 120 g). The last 60% sets strength by pour count (standard 3 × 60 g; fewer/larger = lighter, more/smaller = stronger).
- Method content: `references/methods-seed` — ship all 18 verbatim, including flagged items (the 2026 Multi-Pour is marked single-source; there is NO Devin Chapman record — none could be verified; do not invent one).

**(c) Drippers — catalogue grid + My Shelf.**
- **Catalogue:** all 34 seeded drippers in a **3-in-a-row photo grid** (§Photos). Tile: real photo, name, maker (small), **★ "On your shelf"** badge when owned. **No prices anywhere.** The tile photos are obtained by executing the **framed photo-research prompt** (`references/dripper-photo-pack.md`) with the builder's own research — a mandatory build step executed with the seed, not an optional asset hunt afterwards. The skill ships no photo sources for this; the builder finds them.
- Tap a tile → **full-width detail panel below the row**: geometry, materials, sizes, filter, flow, cup, forgiveness, strengths, weaknesses, source links.
- **My Shelf filter:** shows only owned drippers (starts empty — the user onboards their shelf by marking drippers owned; onboarding is a first-class flow, like bean onboarding).
- **Living registry:** the catalogue grows after launch — a separate **monthly dripper-market scan** (§9) re-scans the whole dripper market and adds genuinely new drippers as full entries (researched specs, photo obtained via the framed photo-research prompt, `owned: false`, badged **New** until the next monthly scan). The ~15-day Explore/News refresh does **not** grow the registry, and no cycle ever removes existing entries.
- Registry content: `references/drippers-seed` — ship all 34 verbatim.

### 2.4 Explore
- Cards for new beans buyable in the user's market: page-preview photo, bean name, roaster/seller, origin, process, roast level, tasting notes, one **why-line**, and the **bag price as listed** on the seller page (prices are allowed HERE only).
- Every card links to the **seller's product page** — mandatory; blog posts and roundup pages are not items.
- Refresh row: `Last refreshed: <date, time> · refreshes about every 15 days` + **Refresh now**.
- Framework defaults for picks (configurable): light-roast, fruity/floral-leaning beans from overseas roasters, buyable locally; seller product pages only.

### 2.5 News
- Two sub-feeds: **Singapore** and **Global**, filterable by the five fixed tags: **Singapore Specialty · Cafes & Events · Global Trends · Drippers & Gear (Hario first) · New Brew Methods**.
- Card: page-preview photo, headline, **ONE-line preview (~15 words max)**, source name + published date, tag chip, **mandatory source link** (no link → the item is never saved).
- **Revolutionary badge:** items flagged revolutionary (a genuinely new dripper/method/gear leap) get a **gold ★ Revolutionary badge** and sort first within their feed.
- Inclusion bar: only news genuinely interesting and usable to a specialty drip brewer — no filler, no generic listicles.
- Same refresh row as Explore (shared refresh).

## 3. Data model & actions

Full field-by-field model and the complete actions catalogue are in `references/design-and-data-spec.md` §2–3. Load-bearing points:

- Tables: `beans`, `recipes`, `brew_methods`, `drippers`, `bean_brew_recs`, `explore_items`, `news_items`.
- **`updatebean` FULL-PAYLOAD RULE:** the update action resets any field not supplied to its schema default. Every update call carries the bean's full current field set. Photo changes go through dedicated photo-only actions and are verified byte-identical on all other fields afterwards.
- Explore is replaced wholesale per refresh; News is replaced per region.
- `getbrewlibrary` returns methods + drippers + recs and powers the Brew tab.

## 4. Freshness engine

Freshness is **computed**, never typed: store roast date + roast level (+ buy date when roast date is unknown — then age from buy date and label it an estimate) and derive the stage **per method**. Drip stage is the default display.

### 4.1 Drip clock (primary) — whole bean, airtight, cool/dark
| Roast | Resting until | Peak | Good until (Drink Soon ends) | Past prime for drip |
|---|---|---|---|---|
| Light | ~day 5 | **day ~7–21** | day 35 | > day 35–40 |
| Light-Medium | ~day 4 | **day ~7–16** | day 30 | > day 30–35 |
| Medium | ~day 3 | **day ~5–12/16** | day 30 | > day 30–35 |
| Dark | ~day 2 | **day ~3–10** | day 21 | > day 21–30 |

Stage flow: **Resting → Brew Now → Peak → Drink Soon → Use for Cold Brew → Past Prime**
- **Resting:** age < rest end. "Opens in N days." Excluded from picks unless nothing else exists.
- **Brew Now:** rest end ≤ age < peak start (peak start ≈ rest end + 2–3 days). "Just opened up — try it this week."
- **Peak:** peak start ≤ age ≤ peak end. Top-ranked.
- **Drink Soon:** peak end < age ≤ good end. "Still good — finish before <good-end date>."
- **Use for Cold Brew:** age > good end but still inside the cold-brew window — hidden from drip picks, surfaced in the cold-brew rescue list.
- **Past Prime:** age > ~60 days, or the user marks it flat/no aroma. Suggest cold brew, cooking, or discard; never auto-delete. Sensory override beats the calendar; mould/damp/musty → **Discard** immediately at any age.

### 4.2 Secondary clocks
- **Espresso:** rest 7–21 d; peak light ~14–28 d, medium ~7–16 d, dark ~5–12 d; usable to ~45–60 d.
- **Cold brew / immersion:** rest ~10–14 d; peak ~14–40 d; the salvage route for past-drip-prime beans (long cold steep foregrounds surviving chocolate/sweet notes).

### 4.3 Modifiers
- **Ground coffee:** divide all windows by ~5–7; show "brew now" immediately.
- **Process (heuristic, label as such):** naturals/anaerobic hold +3–5 days at the tail; light washed −3–5 days at the tail. A nudge, never a separate clock.
- **Altitude:** ≥1,800 m and light roast → +2 days rest.
- **Frozen portions:** freeze the drip stage at its freezing-time value; run a separate **90-day freezer countdown** (freezing slows, not stops, staling).

### 4.4 Ranking & reminders
- **Brew First ranking (drip):** Peak first, **oldest peak first**; then Brew Now; then Drink Soon, nearest good-end deadline first. (FIFO by roast date within a stage.)
- **Reminder triggers:** ① a bean enters drip peak tomorrow · ② 3 days before good-end · ③ on good-end, offer the cold-brew rescue move · ④ freezer expiry at 90 days; thawed portion → use within 48 hrs · ⑤ a bag drops under 40 g · ⑥ total room-temperature stock exceeds ~4 weeks of consumption → prompt to freeze or gift the excess.
- Proactive freshness telling is a core behaviour: the app (and the agent operating it) tells the user what to brew first, what's at peak, what's expiring and what to rescue as cold brew — the user never has to track freshness themselves.

## 5. Tasting-note families & moods

Normalise every bean's printed tasting notes into the **7 families** at intake (keep the original text too):
1. **Berry / Fruity** — berry, stone fruit, tropical, dried fruit
2. **Citrus / Bright** — lemon, lime, orange, grapefruit, bergamot, green apple
3. **Floral / Tea** — jasmine, rose, hibiscus, blossom, black tea
4. **Chocolate / Nutty** — chocolate, cocoa, hazelnut, almond, walnut
5. **Caramel / Sweet** — caramel, honey, brown sugar, vanilla, maple, toffee
6. **Spice / Warm** — cinnamon, clove, nutmeg, cardamom, pepper
7. **Fermented / Funky** — wine, boozy, fermented fruit, cola, yoghurt tang
(Off-notes — papery, woody, ashy, musty — are a staleness flag, never a family.)

**Moods (plain language → software definition, drip-first):**
- **Fruity:** Family 1 dominant; prefer natural/anaerobic, light/light-medium, at Peak.
- **Fresh:** Families 2+3 dominant; washed, light, high-altitude, citrus/floral; freshness stage must be Peak or Brew Now ("fresh" is also a freshness claim).
- **Classy Unique:** rarity + distinctiveness — Family 3 or 7 present, unusual process/variety (anaerobic/carbonic, Gesha/rare), a story bean; **never** a Drink Soon / Past Prime rescue bean.
- **Normal / Cold Brew:** Families 4+5 dominant; medium/medium-dark, chocolate/caramel, forgiving; for cold brew it may also draw on Drink Soon / past-drip-prime beans (served with the 1:8–1:10 cold brew recipe).
Scoring sketch: family match + process bonus + roast bonus + freshness bonus (Peak +3, Brew Now +2, Drink Soon +1 for everyday/cold-brew only). Always show the one-line "why".

## 6. Bean → dripper recommendation engine

Every bean gets a recommendation at intake, shown on its card/detail, and re-mapped whenever the owned shelf changes.

**Output shape (per bean):** ideal dripper + method + why · alternative · **shelf pick** (best dripper from the user's OWNED shelf) + its method + why · source badge.
**Shelf-first rule:** the recommendation LED is the shelf pick — recommend from what the user owns first. The researched ideal shows second, and only matters when it isn't owned (if ideal ∈ shelf, shelf pick = ideal). When the shelf is empty, the ideal leads and no shelf pick is shown.
**Badging:** `Researched pick` when the pick comes from research on that bean/profile; `Generic rule` when it comes from the fallback tree. Never present a generic pick as researched.

**Rules (apply in the fallback tree's order — process sets the ceiling, roast sets the family, dose sets the size):**
- **R1 Roast → temp/grind/agitation:** light/dense = hotter (boiling–96 °C), finer-or-equal, more agitation/pulses, ratio 1:16–1:17. Dark/medium-dark = cooler (83–90 °C), coarser, fewer pours, less agitation. Never fix a roast problem by changing ratio first.
- **R2 Process → solubility & "funk budget":** washed → 94–96 °C, full percolation, cone clarity rewards it. Natural → 90–92 °C working centre, coarser, gentler, less agitation; immersion/hybrid is a recognised gentle route. Honey → 92–95 °C, moderate agitation, flat-bed sweetness. Carbonic/anaerobic/extended ferment → **90–92 °C hard cap**, medium-coarse, gentle equal pulses or hybrid immersion finish; brewers that organise (flat-bed, Origami-wave, Switch) over brewers that amplify acidity.
- **R3 Altitude ≥1,800 m:** treat as one roast step lighter (+1–2 °C, slightly finer or more pulses, longer bloom). Altitude never overrides process.
- **R4 Family → geometry:** floral/citrus/tea → conical paper-forward (V60, Origami-cone, Chemex for batches, Deep 27 single cup). Chocolate/nutty/caramel/spice → flat-bed (Kalita Wave, April, Stagg [X], OREA) or Switch immersion. Fermented/fruity/winey → flat-bed or hybrid (OREA, Origami-wave, Switch, Kalita) or osmotic centre-pour. Berry-jam naturals: never default to Chemex (thick filter strips the jam body).
- **R5 Mechanisms (log these):** flow rate (dripper-metered = consistent; user-metered = skill), bypass (low/zero bypass → more intensity/sweetness at the same ratio; more bypass → cleaner/thinner), bed depth (match brewer size to dose FIRST: 12–16 g → small/deep; 18–25 g → 02/185/M; 30 g+ → 185/03/Chemex), agitation budget (high-fines coffees — Ethiopians, naturals — get less).
- **R6 Troubleshooting steer:** stalls/muddy/astringent → cone → flat-bed or immersion, fewer pulses, lower pour height, −2 °C. Hollow/sour/thin → flat → cone, add a pulse, raise temp, lengthen bloom.

**Generic fallback tree (only roast + process known):**
1. **Process (temperature/agitation ceiling):** washed → 94–96 °C light / 92–94 °C medium, normal agitation, percolation · honey → 92–94 °C, moderate, flat-bed preferred · natural → 90–92 °C, coarse-ish, gentle; hybrid/immersion allowed · anaerobic/carbonic/co-ferment → 90–92 °C hard cap, medium-coarse, gentle pulses or Switch hybrid · unknown → treat as washed if light, as natural if it smells fruity/boozy ("when in doubt, brew cooler").
2. **Roast (brewer family):** light/Nordic → V60 + Hoffmann (washed) or Origami (any process), 1:16–1:17 · light-medium → Switch hybrid (the default for unknown beans — highest success rate) or OREA/Kalita pulses, 1:16 · medium → Kalita Wave standard or April 2-pour, 1:15–1:16 · medium-dark/dark → Switch straight immersion or Mugen one-pour, 85–90 °C, 1:14–1:15, fewest pours.
3. **Dose (size, overrides family ties):** ≤16 g → Deep 27 / V60 01 / Wave 155 / April / Stagg [X] · 17–28 g → V60 02 / Wave 185 / Origami M / OREA Large · ≥30 g → Wave 185 / V60 03 / Chemex 6–8.
4. **Nothing known at all:** Hario Switch, Coffee Chronicler hybrid, 20 g : 300 g, 93 °C, medium grind — it fails sweet and drinkable. Second default: Kalita Wave 185 standard at 93 °C.

## 7. Storage guidance (Beans tab content)

Hot-humid defaults (the framework's home climate assumption): ambient humidity ~82% vs an ideal <60%; enemies in order **oxygen > humidity > heat > light**.
- One active bag (≤250 g) at the counter in an **opaque airtight canister**, coolest dark cupboard, away from stove/kettle/sun. A valve bag is fine unopened; once opened it is not airtight storage.
- Overflow is **portioned and frozen once**: rest 7–10 days first, portion into single-use doses, vacuum/air-pressed bags, ~−18 °C; **90-day freezer countdown** in-app. Thaw sealed to room temp before opening (default) OR grind straight from frozen (true single doses). **Never refreeze.** Never cycle a big bag in and out.
- **Fridge: never** (humid, odour-absorbing, condensation on every removal) — show as an explicit myth card.
- Rotation: strict FIFO by roast date, counter pool and freezer pool separately; a thawed portion jumps the queue.
- Sensible stock: warn when room-temperature stock exceeds ~4 weeks of the user's consumption (~315–420 g at 15–20 g/day).

## 8. Photos (three rules, all mandatory)

1. **Drippers:** every registry dripper has a **real photo of that exact dripper**, sourced from the maker's or a reputable retailer's product page, **visually verified** against the product it labels, **downloaded and bundled as a local app asset** — never hotlinked, never a photo of a different dripper. If a verified photo genuinely cannot be obtained, ship a clean neutral placeholder and flag the dripper by name in the build notes — substitution is forbidden. **How each photo is obtained is a build step of its own:** the seed data carries no photos, so execute the **framed photo-research prompt** in `references/dripper-photo-pack.md` alongside the seed, researching each dripper's photo yourself — the skill deliberately ships no photo sources or bytes for this step. **Parity gate: a build is NOT at parity until every dripper tile shows its verified bundled photo, or a named placeholder exception flagged in the build report.** The same framed prompt also supplies the photo for any dripper the living registry adds later (§9, on the monthly market scan): new entries start `owned: false` and are badged **New** until the next monthly scan.
2. **Beans (default display photo):** at intake, search the web simply — **roaster brand + bean name** — and if the **exact bag's** own product photo is found, download it as the bean's default display photo (source page stored and shown in the detail). If not found: **no substitute** — the user's own bag photo, **nicely cropped** (centred on the bag, tidy edges, scale/clutter cut out), becomes the default. The user's original photo is always kept (`photoUrl`) and viewable in the detail as "Your own photo of this bag".
3. **News & Explore previews:** the card photo is the **source page's preview**, obtained at save time by running this **fallback chain — all three steps, in order, as one procedure** — until a photo is stored:
   1. the page's **og:image**;
   2. the page's **own main content photo** — scan the article body / `srcset` for the page's principal image (many article pages carry their photo only as a main content image, with no og:image at all — a fetcher that tries og:image alone WILL miss them);
   3. a **screenshot-style preview of the page**, rendered by an **external screenshot service** (e.g. WordPress mShots), **downloaded once and stored as an owned blob** — never hotlinked from the screenshot service either.
   The photo is fetched **at save time by the app itself** and stored as an owned blob (a batch must never land photoless because a research step forgot to attach images; a backfill repair action re-fetches any stored row that has a link but no photo, running the same chain). **Runtime limitation — do not attempt in-runtime screenshots:** the artifact action runtime cannot render web pages (its bundled browser cannot screenshot), so step 3 always goes through the external service; steps 1–2 are plain fetches of the page and its image. This chain is the save-time procedure for **both News and Explore** — no feed gets a shorter version of it.

## 9. Refresh (Explore + News)

- **Cadence — two separate cycles:** (1) a silent scheduled Explore/News refresh **about every 15 days**, plus **Refresh now** anytime — this cycle covers **News and Explore only** and never grows the dripper registry; (2) a silent **monthly dripper-market scan** on its own monthly schedule, which is the registry's only growth cycle (framed prompt below). Between runs the tabs show the previously refreshed data with the `Last refreshed: <date, time>` line. (Date AND time — the stored batch timestamp is a full ISO timestamp.)
- **The standing prompt (keep it this simple — do not stack extra rules onto it):**
  > Search the latest coffee news and new beans from the **last 14 days** only. Keep: Singapore specialty coffee, cafes and events; global drippers and gear (**Hario first**); new brew methods; big coffee trends; and new light-roast fruity beans buyable in Singapore from overseas roasters. For every item provide: a photo if available, a headline, a **one-line preview**, a tag from the fixed set, and the **source website link — an item with no link is skipped**. Skip anything older, generic, or not genuinely useful. Newly released drippers you spot are **news items like any other** (tag them Drippers & Gear) — do **not** add registry entries on this cycle; the registry grows only on the separate monthly market scan.
- **Living registry — monthly dripper-market scan:** the registry's growth mechanism is its own cycle, on a **monthly** schedule (a monthly cron), separate from the ~15-day refresh above. The ~15-day refresh does **not** add registry entries — it may surface new-dripper stories in News/Explore, but registry additions happen only on this scan. The scan runs this framed prompt:
  > Once a month, re-scan the whole dripper market: search broadly for drippers released or newly available since the last scan — makers' new releases, reputable retailers' new-arrival ranges, and dripper news from the last ~month. Compare every candidate against the app's **current registry** (the seed plus every dripper previous scans have added). For each **genuinely new** dripper not already in the registry, add it as a **full entry** — researched specs in the registry's field format (name, maker, geometry, materials, sizes, filter, flow, cup, forgiveness, strengths, weaknesses, source links) — with a photo obtained by executing the framed photo-research prompt (§8 rule 1 / `references/dripper-photo-pack.md`), **`owned: false`**, and badged **New**. **Dedupe:** a dripper already in the registry — under the same or a slightly different name, or as another size/material of an existing record — is not added again. **Never remove or overwrite an existing entry**, and never change an `owned` flag. The previous scan's **New** badges expire when this scan runs; this scan's additions carry the badge until the next monthly scan.
  The registry the user browses is therefore the seed **plus** every dripper the monthly scans have added since.
- Save semantics per §3. News previews are enforced to one line on save. At save time the app runs the full **§8 rule 3 photo chain** for every News **and** Explore row — og:image → main content photo → external screenshot preview — as one procedure for both feeds; a row is not completely saved until its photo is stored or the chain has genuinely run out.

## 10. Empty states (framework ships empty — these are the first-run experience)

- **Beans / Overview:** "No beans yet" — a friendly empty state explaining intake (send front + back photos of a bag; fields are extracted and researched for you) with the add form available. Overview shows no hero, no tiles, no mood results until at least one bean exists.
- **My Shelf:** empty until the user marks drippers owned; the catalogue still browses fully, and recommendations lead with the researched ideal (no shelf pick shown).
- **Explore / News:** empty until the first refresh runs; the refresh row shows Refresh now and no "Last refreshed" date.
- **Recipes:** no saved recipes; the four Brew Studio presets are always available.

## 11. Build & verification checklist

1. Create the app as **Best Bloom** with the bean sidebar icon; seed `brew_methods` (18) and `drippers` (34) from `references/` via an idempotent seed action; beans, recs, recipes, Explore, News start empty. **In the same build, execute the framed photo-research prompt** (`references/dripper-photo-pack.md`) using your own research: bundled, verified photo assets for the registry — the seed alone does not produce them, and the skill ships no sources for them.
2. Implement the 5 tabs exactly as §2; verify: Overview ranking + tiles count correctly on test beans; the 4:6 dial rewires pours (40+80 / 60+60 / 80+40); cold brew and ice drip are separate presets with the §2.3 definitions.
3. Verify the safety rules: a partial `updatebean` is impossible from in-app paths (full payloads everywhere); photo-only actions leave all other bean fields byte-identical.
4. Verify photos (**parity gate**): every dripper tile shows its own verified bundled photo (34/34, zero broken, none substituted) — or the build report names each placeholder exception and the build is reported as **not at parity**; no price string appears anywhere in the Drippers UI.
5. Verify refresh: a manual refresh saves News/Explore rows that ALL carry photo + one-line preview + tag + link; rows without a link are dropped; "Last refreshed" renders date and time. Photo verification follows the §8 rule 3 chain — include in the test set at least one source page with **no og:image** (its photo must arrive via the main-content-photo or screenshot route, on either feed). Also verify the two schedules exist **separately**: the ~15-day refresh (News/Explore only — a refresh run adds **no** registry entries) and the monthly dripper-market scan (a simulated scan adds a genuinely new dripper once — full entry, photo via the framed prompt, `owned: false`, badged **New** — and a second run does not duplicate it).
6. Verify recommendations: a new bean gets a rec at intake with the correct badge; marking a dripper owned re-maps shelf picks; with an empty shelf, ideals lead.
7. Phone-width pass: catalogue grids hold 3-in-a-row without overflow or distorted photos; detail panels open full-width below the row.
