# Dripper Registry Seed — 34 records (framework content, ship in full)

Field set per record: slug, name, maker, geometry, materials, sizes, filter, flow, cup, forgiveness, strengths, weaknesses, sourceUrls[], owned.

FRAMEWORK RULES applied to this seed: (1) `owned` is false for every record — the shelf starts empty and the user onboards their own drippers. (2) NO PRICES: the live app carried a priceBand field; the framework drops it — never store, seed or render a price for a dripper. (3) Every record also carries a bundled local photo asset (see SKILL.md §Photos) — photos are sourced from the maker's or a reputable retailer's page for that EXACT dripper, visually verified against the product, downloaded and bundled at build time; never hotlinked.

## Hario V60  (`hario_v60`) — Hario (Japan)

- Geometry: Conical, 60° cone, spiral ribs, single large hole — flow is controlled by you (grind + pour), not the dripper.
- Materials: Plastic/AS resin, glass, ceramic, stainless/metal, copper. Plastic has the best heat-retention-to-preheat ratio and is the Hoffmann/Rao-preferred material functionally; ceramic is heaviest with the highest thermal mass (preheat thoroughly or it steals 4–6°C early); glass is fragile; metal conducts heat away fastest.
- Sizes: 01 (1–2 cups), 02 (1–4 cups — the default; buy this one), 03 (1–6 cups)
- Filter: V60 cone paper, size-matched (01 paper in an 02 leaves a bypass gap; 02 in an 01 crumples and chokes). CAFEC Abaca and Sibarist FAST are common upgrades.
- Flow: Fast, with high bypass potential — water can run down the rib channels.
- Cup: Bright, layered, high clarity, light-medium body. The most expressive — and most punishing — dripper in the registry.
- Forgiveness: Low
- Strengths: Cheapest entry, universal recipe support, highest skill ceiling, 02 filters everywhere.
- Weaknesses: Unforgiving: sour/astringent swings with grind or pour errors. Small doses in an 02 make a shallow bed — use an 01 under 15 g.
- Owned: false

## Hario Switch  (`hario_switch`) — Hario (Japan)

- Geometry: A V60 glass cone (spiral ribs) on a silicone base with a stainless ball valve and PCT resin switch: open = V60 percolation, closed = full immersion.
- Materials: Glass cone as standard; ceramic colour editions of the 02 also sold. Includes 40 V60 filters.
- Sizes: 02 and 03. Note: listings disagree on the 02's practical capacity (200 ml in most; 360 ml figures in some listings are the 03 in Hario's own sizing).
- Filter: V60 02 or 03 paper, size-matched.
- Flow: Binary by valve, then V60-like on release. Drawdown can be slow after a long steep as fines settle — swirl gently before opening.
- Cup: Spans the whole Switch recipe family: from round immersion sweetness to near-V60 clarity, depending on the recipe.
- Forgiveness: High
- Strengths: The most versatile single dripper in the registry; rescues difficult coffees; beginner-proof in immersion mode.
- Weaknesses: Glass fragility, small practical capacity in the 02, drawdown stalls if ground too fine, more parts to clean.
- Owned: false

## Hario Mugen  (`hario_mugen`) — Hario × Tetsu Kasuya (Japan)

- Geometry: V60-02 shape with NO internal ribs — the paper sticks to the wall, and flow exits via star-shaped grooves at the base, deliberately slowing and stabilising drawdown so a single pour works.
- Materials: Plastic (clear/black) original; ceramic editions also sold.
- Sizes: 02 only (1–2 cups)
- Filter: V60 02 cone paper.
- Flow: Slow and fixed, with low bypass (paper sealed to the wall). Minimal user control, by design.
- Cup: Balanced, sweet, integrated; less aromatic layering than a V60.
- Forgiveness: Very high
- Strengths: Easiest good cup in the registry; no gooseneck or bloom technique needed; cheap.
- Weaknesses: One trick — you cannot speed it up or add agitation meaningfully. The fine-grind official recipe can stall with high-fines grinders or coffees.
- Owned: false

## Kalita Wave 155 & 185  (`kalita_wave`) — Kalita (Japan)

- Geometry: Flat-bed, fluted (wave) filter held off the walls, 3 small holes metering the flow.
- Materials: Stainless steel, glass, ceramic — including Hasami-yaki ceramic (Kalita × Hasami, HA-155/HA-185) and Mino-ware ceramic editions. Buy ceramic or glass: the flat steel base lets the wet filter suction onto the holes and stall; ceramic/glass have raised ribs that prevent it.
- Sizes: 155 (1–2 cups), 185 (2–4 cups)
- Filter: Proprietary Kalita Wave 155 / 185 fluted paper only, size-matched.
- Flow: Moderate and dripper-metered. A shallow, even bed means even extraction.
- Cup: Sweet, round, balanced; medium body; moderate clarity.
- Forgiveness: High
- Strengths: Forgiving and consistent; great at larger doses (bed depth scales well in the 185).
- Weaknesses: Filters cost more and are mail-order in many places; flutes collapse if mishandled; the steel version stalls; low skill ceiling — you cannot push the flow.
- Owned: false

## Origami Dripper  (`origami`) — Origami Japan (Trunk Coffee design, Mino, Gifu)

- Geometry: Conical with 20 deep vertical ribs creating large air channels; single 25 mm hole. Dual-personality: with a cone filter it is a fast V60-like cone; with a Kalita Wave filter seated into the ribs it becomes a flat-bed brewer.
- Materials: Ceramic Mino-yaki porcelain (S and M); “Air” versions in AS resin — lighter, more durable, slightly different thermal behaviour. Holder sold separately for the ceramic.
- Sizes: S (1–2 cups), M (1–4 cups)
- Filter: V60 01/02 cone paper OR Kalita Wave 155/185 (M takes 185, S takes 155), plus Origami's own.
- Flow: Cone mode: fast — more airflow than a V60, bright, high clarity, more bypass. Wave mode: slower, less bypass, fuller, rounder, sweeter. The grind must be recalibrated between modes.
- Cup: Bright and clear in cone mode; round and sweet in Wave mode. Two brewers in one.
- Forgiveness: Medium
- Strengths: Two brewers in one; competition-proven (2019 and 2023 World Brewers Cup winners brewed on Origami); beautiful.
- Weaknesses: Ceramic is fragile and needs the holder; fast cone mode can under-extract if poured like a V60 without adjusting; choice overload for beginners.
- Owned: false

## CAFEC Flower Dripper  (`cafec_flower`) — CAFEC / Sanyo Sangyo (Japan)

- Geometry: Conical, 60° bottom angle, deep flower-petal ribs running top-to-bottom that hold the paper off the wall and keep flow moving even as fines accumulate.
- Materials: Porcelain, plastic, and Eastman Tritan editions.
- Sizes: Cup 1 (1–2 cups), Cup 4 (2–4 cups)
- Filter: Cone paper in Cup 1 / Cup 4 size. CAFEC's own papers are the point of the system — match the paper to the roast using CAFEC's range (light/medium/dark roast papers run at different flow speeds): a second control dial no other maker offers.
- Flow: Moderate-fast, and very resistant to stalling versus a V60. Designed for Osmotic Flow: sweet, clean, forgiving of centre pours.
- Cup: Sweet and clean; the osmotic-flow house brewer.
- Forgiveness: Medium-high
- Strengths: The paper ecosystem; stall resistance; works with both osmotic and normal spiral technique.
- Weaknesses: Less ubiquitous outside Japan and Australia; the rib design gives slightly less pour-control feel than a V60.
- Owned: false

## CAFEC Deep 27 (and Deep 45)  (`cafec_deep27`) — CAFEC / Sanyo Sangyo (Japan)

- Geometry: A narrow, deep cone: 27° bottom angle (Deep 27, one cup) creating an unusually deep filtration layer at small doses — the shallow-bed problem every other small dripper has, solved geometrically. Deep 45: 45° angle, for 3–7 cups. Flower-petal ribs vary in height toward the hole so flow doesn't drop despite the narrow angle; single large hole.
- Materials: Deep 27 in Tritan (clear/black/colours). Deep 45 in porcelain/Tritan.
- Sizes: Deep 27 (1 cup), Deep 45 (3–7 cups)
- Filter: Proprietary CAFEC Deep 27 / Deep 45 Abaca+ papers — a lock-in; standard cone papers do not fit correctly.
- Flow: Moderate. The deep bed gives a long contact path for a single cup.
- Cup: Concentrated sweetness, body and clarity together. Osmotic Flow is the house method.
- Forgiveness: High
- Strengths: Best in the registry for a true single cup (10–20 g); forgiving centre pour.
- Weaknesses: Proprietary filters; the Deep 27 cannot scale up; the narrow cone looks and feels unusual and needs stand clearance when brewing into a cup.
- Owned: false

## April Brewer  (`april_brewer`) — April Coffee (Copenhagen, Patrik Rolf) × Serax

- Geometry: Flat-bed with a wide, shallow bed and three “filter holder” wedges holding the paper off the base, plus air pockets in the walls — flow is regulated by the brewer toward a slow, even drawdown.
- Materials: Ceramic (Serax kit with cup and lid) and Plastic 2.0 (Makrolon polycarbonate, made in Indonesia) — unusually expensive for plastic because it is a low-volume design object. A glass Hybrid (immersion) April brewer is also now sold, outside this record's scope.
- Sizes: One size — a one-cup brewer; optimal dose 12–14 g
- Filter: April's own small/large flat papers, or Kalita 155/185.
- Flow: Slow-moderate, low bypass.
- Cup: Sweet, balanced, transparent — and the flavour holds as the cup cools (the design goal). Purpose-built for the April 2-pour structure.
- Forgiveness: High
- Strengths: Consistency; Nordic-light-roast transparency; thermal stability (Plastic 2.0).
- Weaknesses: Price; small optimal dose; slow drawdown with high-fines coffees if you import a V60 grind.
- Owned: false

## OREA V3 / V4  (`orea`) — OREA (London)

- Geometry: Flat-bed with a patented open ring base — the filter is supported on a ring, leaving most of the bed's underside open: the fastest flat-bed in the registry. The V3 Mk2 adds 32 teeth around the bed, creating air pockets that prevent clogging with flat papers and fine grinds. A true flat bed — no prongs or grooves under the paper.
- Materials: V3/V3 Mk2: recycled plastic / polycarbonate with interchangeable bases. V4: Narrow (73°, 12–28 g) or Wide (65°, 12–36 g), each with 4 interchangeable bottoms — Classic (= V3), Open, Fast, and Apex (conical mode, uses folded cone paper): four brewers in one.
- Sizes: V3: Small (155) and Large (185). V4: Narrow and Wide.
- Filter: Kalita Wave 155/185 normally. With OREA's Negotiator tool, flat Sibarist FAST papers can be pressed flat for near-zero bypass.
- Flow: Fast flow permits much finer grinds without choking — higher extraction in less time. Retailer testing reports 1–2% higher extraction versus conventional flat-beds.
- Cup: The signature is high sweetness + high clarity + quality acidity, together.
- Forgiveness: Medium-high
- Strengths: Versatility (OREA claims a grind range “just above espresso to coarse” for the V3); consistency; light and durable; V4 modularity.
- Weaknesses: Price and availability (frequently sold out, batch drops); the Negotiator/flat-paper workflow is extra kit and fuss; fast flow punishes too-coarse grinding with thin cups; plastic-only aesthetic.
- Owned: false

## Chemex  (`chemex`) — Chemex Corp. (design: Peter Schlumbohm, 1941)

- Geometry: A conical top fused to its own glass carafe (hourglass, wood collar and leather tie). Drainage is governed by the filter, not a hole; a spout channel prevents vacuum lock.
- Materials: One-piece glass (Classic line, plus hand-blown and glass-handle lines).
- Sizes: 3, 6, 8 and 10-cup Classic
- Filter: Proprietary Chemex bonded paper, 20–30% thicker than standard — the defining variable: it strips oils and fines aggressively. Filters run about US$12–16 per 100, pricier than V60.
- Flow: Slow — the thick paper sets the pace.
- Cup: Exceptionally clean, tea-like, light body, high clarity; sweetness delicate. Acidity and florals shine; chocolate/body coffees can taste thin.
- Forgiveness: Medium
- Strengths: Batch size; iconic design (in MoMA's collection); unmatched clarity for washed florals.
- Weaknesses: Fragile one-piece glass (a break loses brewer and server together); proprietary, expensive filters; long brew times and over-extraction risk at small doses; poor heat retention in a large glass vessel.
- Owned: false

## Melitta-Style Trapezoid (Wedge)  (`melitta_wedge`) — Melitta pattern — many makers (incl. Bee House / Zero Japan, Kalita 101/102, generic)

- Geometry: Wedge/trapezoid with a near-flat bottom and 1 small hole (classic Melitta) or 2 small holes (Bee House) metering the flow; ribs along the base for airflow.
- Materials: Plastic Melitta cones; ceramic Bee House small/large.
- Sizes: For #1, #2 and #4 wedge papers
- Filter: Melitta-style #1/#2/#4 wedge paper — the cheapest, most available filters in the world (every supermarket). Fold the seams so the paper sits flat.
- Flow: Slow and dripper-metered; very forgiving.
- Cup: Balanced, slightly heavier and softer; less clarity and separation than cone or modern flat-beds; an occasional papery note if the filter is under-rinsed (thicker wedge papers).
- Forgiveness: Very high
- Strengths: Price; filter availability; beginner forgiveness; no gooseneck needed.
- Weaknesses: The single small hole clogs with fines (stalls, uneven extraction); almost no flow control; the lowest ceiling in the registry.
- Owned: false

## Fellow Stagg [X]  (`fellow_stagg_x`) — Fellow

- Geometry: Flat-bed, steep-walled, vacuum-insulated double-wall stainless steel, with a unique hole-and-bump pattern (10 small holes in retailer/Gagné descriptions) for clog-free drainage, and a built-in ratio aid — the dosing funnel doubles as a measure guide.
- Materials: Stainless steel with silicone gasket; matte black/white and wood-accent editions.
- Sizes: [X] (300 ml / 10 oz, one cup) and taller [XF] (600 ml / 20 oz, for “fill-up” immersion-style use)
- Filter: Proprietary Stagg [X] flat-bottom papers (Kalita 185 papers are a loose substitute in practice, not Fellow's spec).
- Flow: Relatively fast for a flat-bed — if the filter doesn't collapse onto the holes (lift the filter walls slightly after rinsing). Thermal stability is the best measured in the registry, which contributes to slightly higher, sweeter extractions; low bypass adds to the sweetness.
- Cup: Sweet and thermally stable; consistent.
- Forgiveness: High
- Strengths: Heat retention; consistency; build and design; the ratio aid for beginners.
- Weaknesses: Premium price; small capacity ([X]); proprietary filters; filter-collapse stalls if set carelessly; the steep walls give a deeper-than-typical flat bed that behaves a little like a hybrid cone/flat.
- Owned: false

## Timemore Crystal Eye  (`timemore_crystal_eye`) — Timemore

- Geometry: Conical, V60-like but with a three-zone interior: smooth top (paper seals, less bypass), grooved middle, and a raised “crystal” texture / concave lower zone that maintains an air gap and smooths and increases flow low in the cone (Timemore's “concave principle”).
- Materials: PCTG/acrylic, glass with holder, and metal-holder editions. (Timemore's separate B75 is a different, flat-bed dripper — not this record.)
- Sizes: 00/01 (1–2 cups), 02 (2–4 cups)
- Filter: Standard V60 cone paper 01/02.
- Flow: Fast, ≈ V60: in head-to-head testing (15 g : 250 g, 5 pours) it matched the V60's 2:40 drawdown, with similar smoothness and more pronounced acidity. Retailer summaries call it slightly more forgiving and predictable-draining than V60 spiral ribs.
- Cup: V60-like, with a touch more acidity.
- Forgiveness: Medium
- Strengths: The V60 ecosystem at V60-or-lower prices; attractive glass; a subtle forgiveness gain.
- Weaknesses: Differences from a V60 are subtle — if you own a V60 it adds little (the comparison site's own conclusion); the holder/collar design is an extra part; brand support and papers outside Asia/EU specialty shops are thinner than Hario's.
- Owned: false

## Hario V60 Kasuya Model  (`hario_v60_kasuya`) — Hario × Tetsu Kasuya (Japan)

- Geometry: The standard V60 60° cone and single large hole — but with customised spiral ribs: deeper and shorter than standard, and they stop before the hole, so the paper sits closer low in the cone and water is held longer. (Some secondary sources also claim a wider outlet; Hario/Kurasu emphasise the rib change — treat the ribs as the real difference.) Model KDC-02-B.
- Materials: Black porcelain/ceramic only in the documented model. Polypropylene measuring spoon included.
- Sizes: 02 only (1–4 cups). W140 × D120 × H102 mm.
- Filter: Hario V60-02 cone paper.
- Flow: Deliberately slower than a standard V60. In Kurasu's back-to-back 4:6 test it was still holding ~2/3 of its water when the classic had nearly finished (Kasuya ~9.5 min to fully drain vs much faster for the classic; TDS 2.14% vs 1.21% — those numbers are test-specific, not a spec). Other tests found a smaller gap (~3:00 vs 2:40): the size of the gap depends on grind and recipe; the direction (slower) is consistent.
- Cup: V60 clarity, but more concentrated, sweeter, rounder and fuller — less bright than the standard V60. Built for Kasuya's 4:6 Method.
- Forgiveness: Medium
- Strengths: Sweetness and concentration with a coarse grind; forgiving for 4:6; premium ceramic feel.
- Weaknesses: Slower — stalls or over-extracts easily with fine grinds or agitation-heavy standard V60 recipes; 02 only, one colour; ceramic is fragile and needs preheating.
- Sources: https://kurasu.kyoto/blogs/kurasu-journal/hario-v60-tetsu-kasuya-model-product-review-back-to-back-comparison-with-the-classic-v60; https://www.aromaespresso.ca/products/v60-dripper-02-kasuya-model; https://www.copancoffeeroasters.com/products/hario-v60-ceramic-dripper-02
- Owned: false

## Hario V60 Dripper NEO  (`hario_neo`) — Hario (Japan)

- Geometry: The V60's first full redesign in ~20 years (launched Jan 2026; iF + Red Dot Design Award 2026). 60° cone, single hole, handle removed — uniform wall thickness gives better thermal distribution, and you hold it by its separable silicone base. The cone angle is even tuned per size (the 01 is 0.4° wider than the 02), and body and base separate so the cone fits the Hario Switch immersion base for percolation / immersion / hybrid use. The redesign is the ribs: 72 ultra-fine ribs line the inner wall and converge seamlessly into 9 outlet ribs at the base — inspired by the Suiren's lesson that rib-to-paper contact controls drawdown (~2 years and 60+ prototypes). Models VDN-01-B / VDN-02-B.
- Materials: Body: PCT resin (Tritan™) — thin, strong, heat-resistant, BPA-free class resin. Base/holder: silicone rubber. Colours: Black (deep black with a subtle green undertone, per Hario), Amber, Clear/Transparent. Made in Japan. Dishwasher safe; NOT for open flame — Kurasu's care note calls it out: this is a resin product.
- Sizes: 01 (1–2 cups, 200–300 ml, Φ108 × H86 mm), 02 (1–4 cups, Φ128 × H103 mm).
- Filter: Standard V60-01 paper for the 01, V60-02 for the 02 — fully compatible with existing V60 papers and Switch bases.
- Flow: Faster than a standard V60, by design: maximum, even drainage down the whole wall, more wall contact, less pooling, less clogging/stalling — without, per Hario, sacrificing depth or concentration.
- Cup: Clean, balanced, low bitterness and muddiness; acidity and sweetness present but not over-pronounced (Kurasu). Other coverage: cleaner, sweeter, brighter. Kurasu's starting recipe: 12 g / 200 ml / 91°C, medium-coarse (a Switch hybrid recipe, 16 g / 240 ml, is also published there).
- Forgiveness: High
- Strengths: Fast and forgiving (pour variation matters less), Switch-compatible, light and unbreakable resin, no preheat soak, cheap for a redesign.
- Weaknesses: Resin, not ceramic/glass/metal — no open flame, and a perceived-premium gap; handle-less handling takes learning; the very fast flow can under-extract coarse/weak recipes if you copy a slow-V60 recipe unchanged; black 01/02 was repeatedly out of stock at Kurasu at research time.
- Sources: https://global.hario.com/neo/; https://kurasu.kyoto/collections/hario/products/hario-v60-dripper-neo; https://eightouncecoffee.ca/products/hario-v60-01-neo-dripper-tritan-black; https://www.yankodesign.com/2026/05/12/harios-v60-gets-its-first-real-upgrade-in-20-years-for-23/
- Owned: false

## Clever Dripper (Mr Clever)  (`clever`) — HandyBrew / Abid (Taiwan)

- Geometry: A Melitta-style wedge/flat-bottom body with handle, lid and coaster — and the defining feature: a shut-off valve in the base, held closed by a base pin while the dripper sits on its coaster or the counter. Coffee steeps by full immersion with no drainage. Set the dripper on a mug or server and the rim pushes the pin up, the valve opens, and the coffee drains through the paper; lift it off and the flow stops. Immersion-only — unlike the Hario Switch it has no open pour-over mode.
- Materials: Eastman Tritan™, BPA-free copolyester.
- Sizes: Small/Standard: 300 ml (W100 × H112 × D118 mm). Large: 500 ml practical capacity (W104 × H133 × D143 mm; fits mug openings ~3.8–9.5 cm).
- Filter: Melitta-style #2 (300 ml) / #4 (500 ml) — retailers describe them as flat-bottom/cone papers; Filtropa #2/#4 are the common substitute.
- Flow: No flow at all until you release it: steep, then a ~30–45 s drain.
- Cup: Fuller and rounder than pour-over, cleaner and sediment-free versus a French press — immersion body with paper clarity. Very forgiving; almost no pour technique. Typical builds: 18–21 g per 300–340 ml, 1:15–1:16.7, medium-coarse, steep 2–3 min (up to 4), total 3–4 min — the steep-time range genuinely varies across credible guides.
- Forgiveness: Very high
- Strengths: Consistency, beginner-proof, cheap widely-available filters, unbreakable, brews straight into the mug.
- Weaknesses: The silicone valve is the wear/leak part over years and needs periodic cleaning/disassembly; plastic body; the large is awkwardly between 1 and 2 full cups; fine grinds clog the drawdown.
- Sources: https://www.coffeehit.co.uk/products/clever-coffee-dripper; https://ozonecoffee.co.uk/products/clever-dripper; https://coffeenerds.co.uk/pages/clever-dripper-recipe-uk; http://eightouncecoffee.ca/products/clever-dripper
- Owned: false

## Hario Suiren  (`hario_suiren`) — Hario (Japan)

- Geometry: No solid cone wall at all: 12 separate petal-like ribs click individually into a base ring/holder, and the V60-02 paper sits exposed in that rib cage — it looks like a flower (suiren = water lily) and you assemble it yourself. The holder can come off so it sits directly on a server or narrower cup, and it flat-packs completely for storage and travel. Model VDSU-02-TB (transparent black; also B&W, Tricolor and Rainbow editions).
- Materials: Ribs: PCT resin. Ring/holder: polypropylene. Made in China (unusual for Hario). Ribs are also sold separately in sets of 6 — the dripper needs 12 — in 7 colours for mixing and customising.
- Sizes: 02 only (1–4 cups). W130 × D125 × H108 mm, ~200 g boxed.
- Filter: Hario V60-02 cone paper.
- Flow: Brews like a V60 (~3:30 in one published test) with a large bottom opening; the open sides allow bypass / side escape — the opposite of no-bypass brewing — and full airflow prevents vacuum-lock. Grind and pour control flow more than the (absent) wall does.
- Cup: V60-like clarity and sweetness, well-aerated. Reviewers position it for experienced V60 users who want fewer wall variables.
- Forgiveness: Medium
- Strengths: Customisable colours, packs flat for travel, unbreakable resin, striking flower look.
- Weaknesses: The petals fall out if you invert it to dump grounds — lift the filter out upright; cleaning 12 small ribs is fiddly; less thermal mass and no wall support for the paper.
- Sources: https://eightouncecoffee.com/products/hario-v60-02-suiren-dripper; https://hario.cc/PDF/2025_English_Catalog_NEW.pdf; https://wafuu.com/en-us/products/hario-v60-dripper-suiren-02-black-1-4-cups-coffee-hand-drip-spiral-rib-vdsu-02-tb
- Owned: false

## Hario Pegasus  (`hario_pegasus`) — Hario (Japan)

- Geometry: A trapezoid/wedge with a flat bottom (Melitta-family shape, not a cone), spiral ribs borrowed from the V60, and two small drain holes that cap the exit rate. Built-in ground-coffee measurement scale, and peep/view holes in the base to check the cup level. Models PED-01-T / PED-02-T / PED-03-T.
- Materials: Transparent AS resin only (in documented listings).
- Sizes: 01 (1–2 cups), 02 (2–4 cups), 03 (4–7 cups).
- Filter: Proprietary Hario Pegasus trapezoid flat-bottom paper (PEF-01/02/03) — do not assume standard Melitta #2/#4 or V60 paper fits.
- Flow: Flow-restricted by the two small holes — water pools over a flat bed even with aggressive pouring. Very forgiving, beginner-oriented.
- Cup: Balanced, sweet, blended — less bright, layered separation than a V60 cone.
- Forgiveness: Very high
- Strengths: Consistency, flat-bed even extraction, dose markings, cheap.
- Weaknesses: Proprietary filters; plastic only; limited top-end clarity and control.
- Sources: https://www.hario.co.uk/collections/hario-pegasus-range/products/hario-pegasus-dripper-clear-size-03; https://wholesale.eightouncecoffee.ca/products/hario-pegasus-02-dripper-plastic; https://www.driproast.com/every-hario-v60-model-explained/
- Owned: false

## Hario V60 Metal & Copper  (`hario_v60_metal`) — Hario (Japan)

- Geometry: Identical V60 cone, spiral ribs and single large hole — the geometry does not differ from the standard V60; the distinction is purely material, thermal behaviour and durability. Metal: VDMR-02-HSV (hairline silver) / VDMR-02-MB (matte black). Copper: VDPR-02-CP.
- Materials: Metal: stainless steel body, silicone holder. Copper: copper body, nickel-plated interior.
- Sizes: 02 only (1–4 cups). Metal W145 × D120 × H90 mm; copper W135 × D120 × H92 mm.
- Filter: V60-02 cone paper.
- Flow: Same flow as a standard V60 for a given recipe; metal heats and cools fast — less heat-soak than ceramic, needs handling care, very durable and travel/outdoors-friendly.
- Cup: The standard clean V60 cup, when preheated.
- Forgiveness: Low
- Strengths: Unbreakable, dishwasher-friendly, premium look (especially the copper).
- Weaknesses: Hot to handle, fast heat loss if not preheated, 02 only, costs several times the plastic V60.
- Sources: https://www.hario.cc/PDF/pdf2024Eng/4.COFFEE_P48-83.pdf; https://mycoffeestage.com/en/products/hario-v60-classic-coffee-dripper
- Owned: false

## Hario V60 Glass & Olive Wood  (`hario_v60_glass`) — Hario (Japan)

- Geometry: Identical V60 cone, spiral ribs and single hole — a material variant, not a new geometry. The glass lets you see the filter, paper and flow as you brew. Glass: VDGR-01/02, VDGN-03. Olive Wood: VDGR-02-OV / VDG-02-OV.
- Materials: Heatproof borosilicate glass. Olive Wood version: olive-wood holder with a silicone inner ring (glass/silicone made in Japan, wood holder made in China, per Hario Asia).
- Sizes: Glass: 01 (1–2), 02 (1–4), 03 (1–6 cups). Olive Wood: 02 only.
- Filter: V60 cone paper, size-matched.
- Flow: Standard V60 flow and cup; glass retains heat well when preheated but is fragile. The olive-wood collar stays cooler in the hand.
- Cup: The standard V60 — bright, layered, high clarity.
- Forgiveness: Low
- Strengths: Visibility while brewing, the look, good heat retention for glass.
- Weaknesses: Breakable; the olive-wood holder needs hand-washing and care; cost.
- Sources: https://mycoffeestage.com/en/products/hario-v60-classic-coffee-dripper; https://hario-asia-official.com/products/hario-asia-official-v60-glass-dripper-olive-wood-02-size
- Owned: false

## Hario V60 Drip Decanter  (`hario_drip_decanter`) — Hario (Japan)

- Geometry: An all-in-one set, not a standalone dripper geometry: a standard 02 polypropylene V60 cone that sits inside / stands over its own 700 ml heatproof-glass decanter, with a removable silicone band/handle. Model VDD-02B.
- Materials: Glass pot + polypropylene dripper + 40 V60-02 papers (made in Japan); silicone band made in China.
- Sizes: 1–4 cups / 700 ml. W135 × D125 × H198 mm assembled, ~600 g boxed.
- Filter: V60-02 paper (40 included).
- Flow: Standard paper-filter V60 flow — a clean cup. Hario's 'ease of paper drip, flavour of cloth drip' line is marketing for the integrated form, not a different filter.
- Cup: The standard clean V60 cup.
- Forgiveness: Low
- Strengths: Cheap all-in-one; the dripper also stands alone.
- Weaknesses: The polypropylene cone is the least-premium V60 material; the decanter form is less flexible than a separate dripper + server.
- Sources: https://alturaenterprise.com/products/hario-v60-drip-decanter; https://www.kaffebox.no/product/hario-v60-drip-decanter/
- Owned: false

## Hario Cafeor  (`hario_cafeor`) — Hario (Japan)

- Geometry: A cone dripper frame with a built-in stainless-steel mesh filter — no paper required (paper can be added in some versions). Dripper: CFOD-1B / CFOD-02-B. Also sold as a dripper-pot (CFO-1B / CFO-2B), and a 'Cafeor Light' sub-variant (CFOL-1BR) uses a polyester filter.
- Materials: Polypropylene frame, stainless mesh. Pot version: heatproof glass pot, polypropylene lid/frame, silicone packing.
- Sizes: Dripper: CFOD-1 (1 cup), CFOD-02 (1–4 cups). Pot: CFO-1B (200 ml), CFO-2B (300 ml practical).
- Filter: Permanent stainless mesh (reusable).
- Flow: The mesh lets coffee oils pass — fuller, richer, more aromatic, less paper-clean; some fines risk compared with the Double Mesh dripper.
- Cup: Fuller and richer than a paper V60, with less clarity.
- Forgiveness: Medium
- Strengths: No paper cost or waste; oils and body; the pot version brews and serves.
- Weaknesses: Mesh cleaning and stale-oil risk; less clarity; small pot capacities.
- Sources: https://www.hario.cc/PDF/pdf2024Eng/4.COFFEE_P48-83.pdf; https://brewinggadgets.in/products/hario-dripper-pot-cafeor
- Owned: false

## Hario Double Mesh Metal Dripper  (`hario_double_mesh`) — Hario (Japan)

- Geometry: An all-stainless cone whose walls are two finely etched mesh layers — the dripper IS the filter. Internal powder markings. Distinct from both the Cafeor and the metal V60. Models DMD-01-HSV / DMD-02-HSV.
- Materials: Entirely stainless steel. Made in China.
- Sizes: DMD-01 (1–2 cups), DMD-02 (1–4 cups; ~480 ml listed capacity from one retailer).
- Filter: None — the double mesh is the filter.
- Flow: Claimed paper-like clarity WITH metal-filter oils and heavier body than a paper V60; only super-fine particles should pass if the grind is right.
- Cup: Fuller than paper, clearer than a single mesh.
- Forgiveness: Medium
- Strengths: Paperless, durable, fuller than paper.
- Weaknesses: Grind-sensitive (too fine clogs, too coarse silts); needs thorough cleaning; premium price for a made-in-China product.
- Sources: https://eightouncecoffee.ca/en-gb/products/hario-02-dual-mesh-filter-dripper; https://www.coffeebeanery.com/products/double-mesh-metal-coffee-dripper
- Owned: false

## KONO Meimon Dripper  (`kono_meimon`) — KONO / Coffee Syphon Co. (Japan)

- Geometry: A cone with a single hole (slightly smaller than the V60's) and 12 straight — not spiral — ribs in the LOWER HALF ONLY. The upper half has no ribs, so the paper seals flush to the wall: no lateral bypass, and water is forced down through the lower rib channels. Generations: MD-21 (1st gen, 'Classic') / MDN-21 (2nd gen, the current standard) / MDK-21 (3rd gen, 90th-anniversary) — rib length shortens by generation (MD > MDN > MDK), and that rib length is the main difference between them (MDK shortest = slowest, least bypass, best for small amounts per one specialist source).
- Materials: Acrylic resin, heat resistance ~90°C. Many limited colour editions (MDN).
- Sizes: 2-cup (~D95 × H65 mm cone) and 4-cup versions.
- Filter: KONO paper, or V60-01 size for the 2-cup (V60-02 class for the 4-cup, per retailers).
- Flow: ⚠ Sources disagree: maker/retailer copy says relatively slow, stable, drop-by-drop — but one controlled V60-vs-Meimon brew-off timed the Meimon FASTER (1:54 vs 2:14) at that grind/recipe. Read it as recipe-dependent: designed to restrict bypass and concentrate flow centrally, not unconditionally 'slow'.
- Cup: Dense, sweet, concentrated, round and thick, with a full aftertaste — often likened to nel drip; especially praised for medium and dark roasts.
- Forgiveness: Medium
- Strengths: A sweetness and density no other cone matches; huge colour range; classic status — KONO is the ancestor conical dripper, pre-dating the V60.
- Weaknesses: Acrylic 90°C limit and durability; the small hole plus sealed upper wall can stall with fines; generation/colour confusion when buying.
- Sources: https://kurasubkk.com/products/kono-meimon-2-person-dripper-color; https://coffeeronin.ca/blogs/about-coffee-gears/introduction-of-hakka-life-six-ridges-dripper; https://comoricoffee.com/en/review-v60-meimon-comparison-en/
- Owned: false

## Torch Mountain Dripper  (`torch_mountain`) — Torch (Kyoto, Japan)

- Geometry: A short, wide, flat-ish base cone with internal stair-like ribs. ⚠ Version flag: the original has a central large hole + 4 small holes (one retailer description); the renewed/current version has a star-shaped indentation with 5 small holes (+ central hole in the Kinsai description) guiding airflow — check which version a listing is.
- Materials: Mino-ware porcelain body; solid beech holder (urethane finish; older listings say white ash — holder wood varies by batch/retailer). Colours: White Matte, Black Glaze, Yellow, plus a hand-gilded Kinsai edition.
- Sizes: 1–2 cups only. Dripper Φ90 × H70 mm, ~178 g; holder Φ110 × H10 mm.
- Filter: Unusually flexible: cone (Hario/Kono 01), Kalita Wave 155, or folded trapezoid — the cup changes with the filter choice.
- Flow: Stable, smooth, well-extracted yet delightfully light.
- Cup: Torch/Kurasu position the Mountain for light roasts: bright acidity with a cone filter; richer and sweeter with a Wave filter.
- Forgiveness: Medium-high
- Strengths: Filter versatility, craft and look, light-roast clarity.
- Weaknesses: Small capacity; porcelain + wooden holder care; version confusion.
- Sources: https://kurasu.kyoto/collections/brewing-gear/products/torch-mountain-drippernew; https://theobjectdepot.com/products/torch-mountain-dripper
- Owned: false

## Torch Donut Dripper  (`torch_donut`) — Torch (Japan)

- Geometry: A tall, slim, deep cone (a deeper bed than the Mountain), internal ribs, one large outlet hole, seating flat on its holder — the 'donut' is the wooden holder's shape, not the cone's.
- Materials: Mino-yaki porcelain; white ash wood holder.
- Sizes: 1–4 cups per most retailers (one says 3 cups max — flagged). Dripper Φ90 × H95–100 mm, ~235–241 g.
- Filter: Folded trapezoid — Kalita 103 / Melitta 1×4 / Cafec 102 recommended (fold to a ~4 cm bottom); a V60-02 cone can be substituted, per one retailer.
- Flow: The large hole gives free, smooth flow; the deep bed emphasises smoothness, body and sweetness.
- Cup: Built for medium-to-dark roasts — the inverse positioning to the Mountain.
- Forgiveness: Medium
- Strengths: Body and sweetness for darker roasts; a beautiful object.
- Weaknesses: Filter-folding faff; tall, fragile porcelain; single size.
- Sources: https://kurasu.kyoto/blogs/kurasu-journal/torch-donut-dripper-brewing-guide-how-we-do-it-at-kurasu; https://int.japanesetaste.com/products/torch-donut-white-porcelain-pour-over-coffee-maker; https://naokoffee.com/product/torch-donut-dripper/
- Owned: false

## Bee House / Zero Japan Wedge  (`bee_house`) — Zero Japan (Mino, Gifu, Japan)

- Geometry: A wedge/trapezoid (Melitta-style) with a flat bottom, two small drain holes, straight ribs, and an open base with peek windows so you can see the cup level without lifting. (The US brand was renamed Bee House → Zero Japan in 2018.) SKUs BKK-15S (small) / BKK-15L (large) class.
- Materials: Ceramic/porcelain only, many colours.
- Sizes: Small: #1 filters, 1–2 cups. Large: #2 or #4 filters, up to ~3–4 cups.
- Filter: Melitta-style trapezoid #1 (small) / #2 or #4 (large).
- Flow: Two holes give a 'just right', restricted, forgiving flow.
- Cup: Clean, sweet, balanced. One guide's starting recipe: 20 g : 320 g (1:16), medium grind, ~3–4 min.
- Forgiveness: Very high
- Strengths: Forgiving, cheap supermarket filters (large), the peek hole, ceramic heat retention, huge colour range.
- Weaknesses: Wedge-bed clarity ceiling below the V60; ceramic is breakable and heavy; the large takes the oversize #4 filter awkwardly.
- Sources: https://www.craftcoffeeguru.com/bee-house-coffee/; https://www.faire.com/product/p_p7xv6xbsqm
- Owned: false

## Suji Drippers  (`suji`) — SUJI (Bandung, Indonesia)

- Geometry: ⚠ Low-documentation / regional entry: specs are marketplace claims (Shopee listings + Indonesian social posts); no independent test was found. Suji V60 01/02: a 60° cone, single bottom hole. Suji Wave 155: flat-bottom wave shape, 5 circular wave ribs, 3 small bottom holes + a raised rib so the paper doesn't stick (a 'Chihiro' edition differs: SAN plastic, single 9 mm hole + 3 supports — hole count varies by edition). Named designs 'Panca' and SD1R semi-immersion appear only in social posts, without verifiable specs.
- Materials: Thick food-grade plastic (V60); SAN plastic (Chihiro edition). Many colours.
- Sizes: V60 01 (1–2 cups, max ~20 g) and 02 (1–4 cups); Wave 155.
- Filter: V60 cone paper / Wave 155 paper, size-matched.
- Flow: By geometry, standard V60-like (cone) or sweet/thicker (Wave, per listing copy) — no independent test found.
- Cup: As per the geometry above; not independently verified.
- Forgiveness: Medium
- Strengths: Very cheap; colour range.
- Weaknesses: Marketplace-only documentation; edition differences (hole counts) are easy to miss when buying.
- Sources: https://shopee.sg/Suji-Dripper-V60-01-(1-2-cups)-and-02-(1-4-cups)-Coffee-Dripper-manual-coffee-brewing-tool-i.555828696.21073972765; https://shopee.sg/SUJI-Pourover-Coffee-Wave-Dripper-155-Pour-Over-V60-Coffee-Brewing-Tool-i.267728402.26653506089
- Owned: false

## LiLi Dripper  (`lili`) — LiLi (design references the Melitta Nr. 102, 1934–1938)

- Geometry: A flat bottom with a steeper wall angle than the Kalita Wave, 48 ribs (8 main + 16 long support + 24 short support) and 8 bottom holes — the intense ribbing keeps airflow smooth, and the redundancy means one or two blocked holes don't stall the brew. Higher bottom support and smaller holes than the Melitta reference.
- Materials: Ceramic (V2.0 standard and Mini). A plastic base on the OEM standard version was noted as a negative by the main English reviewer.
- Sizes: Standard (opening 118 mm, height 80 mm) and Mini (1–2 cups, ~12 g-dose focus in one listing, leaf-shaped base).
- Filter: Fan/trapezoid 102 (the maker's default, recommended) or Kalita Wave 185 — the fan filter runs ~10–15 s slower than Wave in the reviewer's tests.
- Flow: Medium-fast for a flat-bottom; clean, layered flavour, less clogging worry.
- Cup: Balanced, full body per V2 retail copy.
- Forgiveness: High
- Strengths: Anti-clog redundancy; dual-filter flexibility.
- Weaknesses: Folding a fan filter to fit takes time; non-standard base fit; sparse English documentation and retail.
- Sources: https://coffeeronin.ca/blogs/about-coffee-gears/introduction-of-lili-dripper
- Owned: false

## Graycano Dripper  (`graycano`) — Graycano GmbH (Güster, Germany)

- Geometry: A cone (size-1 class) with V-shaped 'Lava Ribs' in an asymmetric spiral pattern that lift the paper and break channels, plus underside Air Pockets — a double-walled geometry that traps rising steam from the server to reheat the body. An optional Graycano Coin insert converts it to flat-bottom (an accessory, not a separate dripper).
- Materials: Cast aluminium with a food-safe silicone-based coating — effectively unbreakable. Original: handmade cork Sleeve Pro. The Dripper S replaces cork with a silicone ring. Not dishwasher-safe.
- Sizes: One core size: top Φ96 mm, bottom Φ98 mm, H66 mm, ~240–250 g.
- Filter: Size-1 conical — Graycano's own GC01 (medium-slow), V60-01, Melitta 101 class.
- Flow: Even, clog-resistant flow plus exceptional thermal stability. Maker-recommended ratio 1:15, medium-coarse grind.
- Cup: Bright, sweet, clear.
- Forgiveness: High
- Strengths: Heat performance, durability, consistency.
- Weaknesses: Premium price; gets hot (must use the sleeve/ring); hand-wash; single small size.
- Sources: https://graycano.com/en/product/graycano-dripper; https://eightouncecoffee.ca/products/graycano-conical-coffee-dripper-w-sleeve-pro; https://www.slowpoursupply.co/collections/graycano/for-conical-brewers
- Owned: false

## UFO Dripper  (`ufo`) — UFO Coffee Tools (Korea)

- Geometry: An 80° interior cone angle (vs the V60's 60°) — a wide, shallow bed, so dose changes move bed depth very little. Recessed air channels instead of protruding ribs: the paper is less likely to seal, air pressure equalises, and stalling/bypass is controlled. V3 cones also sit on a Hario Switch base for immersion/hybrid use.
- Materials: V3 in Tritan (detachable silicone base); also a ceramic version with the same 80° geometry, thicker/heavier walls, variable wall thickness and no detachable base. The earlier V2 Tritan is discontinued in several listings.
- Sizes: V3: 01 (small doses ~12–18 g) and 02 (~300 ml, 1–4 cups). Ceramic: same geometry.
- Filter: UFO's own papers — Type A (medium flow), Type F (fast flow, recommended for the V3) — plus Sibarist UFO FAST / B3. Some listings also claim standard cone papers for ceramic/V2; prefer UFO/Sibarist papers for the V3.
- Flow: A forgiving conical — slower contact than the angle alone would suggest.
- Cup: Clarity and complex acidity with improved consistency, sweetness and balance.
- Forgiveness: High
- Strengths: Dose-forgiving, anti-stall, Switch-compatible, competition visibility.
- Weaknesses: Proprietary filter ecosystem and cost; premium price for a resin cone; version churn (V2/V3/ceramic).
- Sources: https://www.slowpoursupply.co/products/ufo-dripper-v3; https://www.slowpoursupply.co/pages/ufo; https://capecoffeebeans.co.za/products/ufo-v3-02-pour-over-coffee-dripper
- Owned: false

## Saint Anthony F70  (`saint_anthony_f70`) — Saint Anthony Industries (USA)

- Geometry: A flat bottom with a 70° wall angle (the whole SAI '70' system), short and wide. W4.1″ × H3.1″ (104 × 80 mm); bottom ring Φ60 mm (the minimum server/mug opening).
- Materials: Ceramic (white/black/Mahoney brown etc.; Hasami-made ceramic versions are noted in the secondary market).
- Sizes: One size.
- Filter: Proprietary F70 Perfect Paper Filters (flat-bottom, introduced 2019) — not Kalita Wave papers.
- Flow: An even flat bed: consistent, with less brew variability than a cone, by design.
- Cup: Rich, full-bodied, sweet.
- Forgiveness: High
- Strengths: Repeatability; beginner-friendly; thermal stability of dense ceramic (with preheat).
- Weaknesses: Proprietary filters; low versatility ceiling; ceramic preheat soak.
- Sources: https://stanthonyind.com/collections/brewing; https://loom.coffee/collections/home-coffee-brewing-solutions-all/products/f70-ceramics-flatbottom-pourover-brewer
- Owned: false

## Saint Anthony C70  (`saint_anthony_c70`) — Saint Anthony Industries (USA)

- Geometry: A cone at a steep 70° angle — a ~30% taller brew column than standard filters, per retailer copy, so the bed is deep and grounds stay in the bed. System siblings: the G70 (glass, C70 filters) and Phoenix70 (metal, US$69).
- Materials: Ceramic.
- Sizes: One size.
- Filter: Proprietary C70 Perfect Paper Filters (conical, introduced 2018).
- Flow: Conical clarity with a deeper, slightly slower bed than a V60: in Royal Coffee/Crown brew analyses, the C70 at 18 g : 300 g ran ~2:55–3:39.
- Cup: Brighter fruit and a lighter, slightly syrupy cup versus flat-bottom comparators.
- Forgiveness: Medium
- Strengths: Clarity plus depth; a distinctive system.
- Weaknesses: Proprietary filters; ceramic preheat; niche availability.
- Sources: https://stanthonyind.com/collections/brewing; https://www.wholelattelove.com/blogs/articles/pour-over-brew
- Owned: false

## Bonavita Porcelain Immersion Dripper  (`bonavita_immersion`) — Bonavita

- Geometry: DISCONTINUED — secondhand-only. A porcelain steep-and-release cone with a manual open/close lever switch — unlike the Clever's cup-actuated valve and the Switch's ball valve, you can open and close it while it sits on the server — plus a fitted lid to hold heat. Model BV4000IDV2. ⚠ Listing dimensions conflict (lid/box inclusion), so no single dimension set is registered.
- Materials: Porcelain cone; polymer frame/valve parts.
- Sizes: Large: 16 oz / ~470 ml, #4 filters (or a permanent filter). A Small (10 oz, #2) version appears in one Malaysian retailer listing — retailer-reported only.
- Filter: #4 (large) — or a permanent filter.
- Flow: Steep 3–4 min total per the Roastmasters guide, then lever open to drain.
- Cup: French-press-like flavour with paper cleanliness; porcelain heat retention is its edge over the Clever.
- Forgiveness: Very high
- Strengths: Porcelain (no plastic in the brew path except the small valve piece, per owner reports); a positive manual valve.
- Weaknesses: Discontinued; valve/lever breakage is the recurring owner complaint; heavy; wide base fit.
- Sources: https://www.roastmasters.com/bvdripper.html; https://www.coffexcoffee.com/product/bonavita-wide-base-immersion-dripper/
- Owned: false
