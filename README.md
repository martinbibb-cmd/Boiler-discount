# Boiler-discount
Tells you exactly what discounts on what boiler.

## Channel endpoints

- `/` — normal/Inhome discount finder
- `/office-voice/` — standalone Office/Voice list (deliberately not linked from the normal page)

The Office/Voice endpoint includes a `noindex` directive and its data is kept out of
the normal page. This is separation for presentation, not authentication: on a static
GitHub Pages site, anyone who knows the endpoint can access it.
