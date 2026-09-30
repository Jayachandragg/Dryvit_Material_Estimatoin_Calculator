
# Dryvit Outsulation Plus MD : Material Calculator

A self-contained HTML/JS calculator that estimates material quantities for
Dryvit's Outsulation Plus MD EIFS wall system. No build step, no
dependencies , open any version directly in a browser.

## What it does

Given a total wall area (and a few linear measurements — joint length,
opening perimeter), the calculator walks through each required system
component in the same order as Dryvit's own system datasheet, lets you pick
the specific product for each step, and computes how many units to order
based on that product's published coverage rate.

## Version history

| Tag | File | Summary |
|-----|------|---------|
| `v1` | `calculator.html` | Initial build. 7-step generic template — optional steps togglable, ~42 products, no Drainage or EPS Insulation step. |
| `v2` | `calculator_bala.html` | Revision pass on v1. Still missing Drainage and EPS Insulation Board as explicit steps; Flashing folded into Air/Water Barrier. |
| `v3` | `calculator_v2.html` | Full rebuild. 9 required steps in Dryvit's real site order (Accessories → Barrier → Flashing → Drainage → Adhesive → EPS → Base Coat → Mesh → Finish), plus optional Primer/Sealer add-ons. Adds multi-product rows per step, adhesive-vs-base-coat rate filtering on shared products, optgroup product categories, and removes the old flat 10% waste buffer in favor of raw `ceil(area/coverage)`. |
| `v4` | `calculator_v4.html` | Adds AquaFlash Liquid coverage math (container size × mesh width, driven by a "Length of Openings" field), Drainage Strip/Track linear-ft coverage with auto-filled/overridable length inputs, and an Instastick adhesive option. Renames "AquaFlash" to "AquaFlash Liquid" to disambiguate from AquaFlash Mesh. |



## Usage

Open the relevant `.html` file directly in any browser, everything
(product data, calculation logic, styling) is embedded in the single file.
No server, no npm install required.


## Known limitations

- Single-system prototype (Outsulation Plus MD only) , not yet generalized
  to other Dryvit systems.
- Product coverage data is hand-maintained in this file; it is not
  auto-generated from any external catalog, so it can drift out of sync
  with source datasheets if either is updated independently.
