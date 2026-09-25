# Boiler-discount
Tells you exactly what discounts on what boiler.

## Channel endpoints

- `/` — normal/Inhome discount finder
- `/office-voice/` — standalone Office/Voice list (deliberately not linked from the normal page)

The Office/Voice endpoint includes a `noindex` directive and its data is kept out of
the normal page. This is separation for presentation, not authentication: on a static
GitHub Pages site, anyone who knows the endpoint can access it.

## Discount source

Discounts are in pounds and follow `GRFW '26 Boiler List.xlsx`:

- `/`: `Inhome Final DIscount List` (112 boilers).
- `/office-voice/`: `Voice Final DIscount List` (61 boilers).

Match records by trimmed CBLR code. Each page lists only the boilers on its
channel's sheet. The workbook's Online sheet is not used because this repo has
no Online endpoint. Existing boiler prices are retained; newly listed boilers
have no price where the workbook supplies none.
