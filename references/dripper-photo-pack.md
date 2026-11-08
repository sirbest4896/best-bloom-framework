# Dripper Photo Pack — mandatory build step (framed research prompt)

The dripper catalogue is photo-first (§2.3c, §8 rule 1): every tile leads with a real photo of that exact dripper. The seed files (`drippers-seed.json`) carry **no photos**, and this skill deliberately ships **no photo sources and no photo bytes**: builders research and obtain the photos themselves, with their own research and tokens, by executing the framed prompt below. A build that only seeds the data ships placeholder tiles — that build is **not at parity**. This step is a mandatory part of the build, executed alongside the seed (§11 item 1), not an optional asset hunt afterwards.

**Parity gate: a build is NOT at parity until every dripper tile shows its verified bundled photo, or a named placeholder exception flagged by name in the build report (see the prompt's failure path and the acceptance criteria).**

---

## The framed photo-research prompt

Execute this prompt with your own web research for the dripper registry you are building:

> **Photo research — one verified product photo per registry dripper.**
>
> For EACH dripper in the registry seed (`references/drippers-seed.json`), research and obtain one product photo of that exact dripper, using your own web research. This skill provides no photo URLs, no retailer lists and no image files for this step — finding them is the task.
>
> **Where to look (strategy only — no sources are given):** start with the maker's own official store and product pages for that dripper. If the maker has no usable product photo, move to reputable specialty coffee retailers' product pages for that same dripper. Prefer the maker's/retailer's own product shot of the dripper itself; a clean product photo is best, and an in-use shot is acceptable only when the dripper is unambiguous in it.
>
> **Verify before use (acceptance standard):** open every candidate image and confirm it depicts **that exact dripper** — match its shape, rib pattern/geometry, material and colour against the seed record's `geometry` / `materials` / `sizes` fields. Traps to avoid:
> - A dripper sold in several colours or material editions must be pictured in an edition the record actually describes.
> - A variant-specific record (a named special edition or model) must show **that variant**, not the maker's base model.
> - Look-alike models from the same maker are different drippers — do not accept one as another.
> - Where a record covers a product line (multiple sizes/materials), one representative photo of that line is correct.
>
> If a photo cannot be confirmed as that exact dripper, reject it and keep looking.
>
> **Process and bundle:** convert each verified photo to **JPEG, max ~900 px on the longest side**, flatten any transparency onto the app's card cream, and store it as a **local build asset named by dripper slug** (`<slug>.jpg`), mapped in the client by slug. **Never hotlink** a source image URL in the shipped app — the bundled file is the asset.
>
> **Forbidden:** substituting a photo of a different dripper, a generic coffee photo, stock imagery of other brewers, or an AI-generated image.
>
> **Failure path:** if, after a genuine search of the maker and at least two reputable retailers, no photo can be **verified** as that exact dripper, ship that tile with the app's clean neutral placeholder (monogram tile) and **flag the dripper by name in the build report** as a placeholder exception.

## Acceptance criteria

- Every dripper tile shows its own verified bundled photo — or the build report names each placeholder exception, and the build is reported as **not at parity** until the exception list is empty.
- All photos are bundled local assets (zero hotlinks), each visually verified against the exact dripper on its tile, with zero substitutions.
