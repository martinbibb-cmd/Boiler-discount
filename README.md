# Boiler-discount
Tells you exactly what discounts on what boiler.

## Channel endpoints

- `/` — normal/Inhome discount finder
- `/online/` — Online discount finder, linked from the main page
- `/office-voice/` — standalone Office/Voice list (deliberately not linked from the normal page)

The Office/Voice endpoint includes a `noindex` directive and its data is kept out of
the normal page. This is separation for presentation, not authentication: on a static
GitHub Pages site, anyone who knows the endpoint can access it.

## Discount source

Discounts are in pounds and follow `GRFW '26 Boiler List.xlsx`:

- `/`: `Inhome Final DIscount List` (112 boilers).
- `/office-voice/`: `Voice Final DIscount List` (61 boilers).
- `/online/`: `Online Final DIscount List` (41 boilers).

Match records by trimmed CBLR code. Each page lists only the boilers on its
channel's sheet. Existing Inhome boiler prices are retained; newly listed boilers
have no price where the workbook supplies none. Online and Voice show the
discount amounts without boiler prices.
