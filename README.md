# Boiler-discount
Tells you exactly what discounts on what boiler.

## Channel endpoints

- `/` — normal/Inhome discount finder
- `/online/` — standalone Online discount finder
- `/office-voice/` — standalone Office/Voice list (deliberately not linked from the normal page)

The Office/Voice endpoint includes a `noindex` directive and its data is kept out of
the normal page. This is separation for presentation, not authentication: on a static
GitHub Pages site, anyone who knows the endpoint can access it.

## Discount source

Discounts are in pounds and follow `Black Friday 2026 List for Delivery.xlsx`:

- `/`: `Inhome Final DIscount List` (110 boilers, face-to-face).
- `/office-voice/`: `Voice Final DIscount List` (63 boilers).
- `/online/`: `Online Final DIscount List` (54 boilers).

Match records by trimmed CBLR code. Each page lists only the boilers on its
channel's sheet, excluding Ariston boilers as requested.

## Prices

All three pages use the `Part Price (inc VAT)` column from the British Gas UK
Installations Manual Price Book (`068P200000uDkRQ.pdf`), matched by CBLR code.
Prices after discount subtract that page's channel discount from the base price.
The existing Inhome prices match the PDF. Codes `CBLR8011` through `CBLR8020`
are absent from the PDF, so their base and after-discount prices display as `—`.
