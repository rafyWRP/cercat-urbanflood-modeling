# NYC Urban Flood Modeling — Data Inventory

Interactive map and data inventory supporting a study on integrating urban drainage
networks (UDNs) into 2D hydrodynamic flood models via MOSART-Urban and SWMM,
built on the TRITON flood model. This is the data-compilation stage for New York
City, the first of three test cities (NYC, Philadelphia, Chicago).

**View the interactive map:**
[nyc_inventory_map.html](https://yourusername.github.io/nyc-flood-inventory/nyc_inventory_map.html)

## What's in the map

Toggleable layers covering:

- **Watershed boundaries** — HUC2 through HUC12 (USGS WBD), plus HUC14 (NJ side only)
- **Hydrography** — NHDPlus High Resolution and NHDPlusV2 flowlines/catchments
- **Sewer & drainage infrastructure** — DEP MS4 drainage areas and outfalls, NYSDEC
  CSO outfalls and regulated MS4 boundaries, Open Sewer Atlas NYC interceptors and
  sewersheds
- **311 complaint records** — street flooding, basement flooding, and clogged
  catch basin reports, as spatial evidence of real flood impact
- **Gauges** — USGS stream gauges (fluvial) and NOAA CO-OPS tide stations (tidal
  boundary), with period of record and temporal resolution shown on click

Click any gauge for detailed metadata (data availability, resolution, station type).
Use the layer control (top right) to toggle datasets on/off.

## Data sources

| Category | Source |
|---|---|
| Watershed boundaries | USGS Watershed Boundary Dataset (WBD) |
| Hydrography | USGS NHDPlus HR / NHDPlusV2 |
| Stream gauges | USGS NWIS |
| Tidal gauges | NOAA CO-OPS |
| Admin boundaries | NYC Dept. of City Planning (Open Data) |
| MS4 / storm sewer | NYC DEP (Open Data) |
| CSO outfalls, MS4 boundaries | NYSDEC |
| Sewer network (unofficial) | Open Sewer Atlas NYC |
| 311 complaints | Open Sewer Atlas NYC (NYC Open Data derived) |

Full source URLs, fetch dates, record counts, and known caveats for every layer
are tracked in the project's data inventory manifest.

## Known limitations

- HUC14/HUC16 are not meaningfully available inside the five boroughs — sub-HUC12
  discretization currently relies on NHDPlus catchments or DEP drainage areas instead.
- Real-world UDN data at the full-watershed scale is not available; a simulated
  network (BUSN) is used instead, which assumes separate storm sewers only —
  a mismatch for NYC's combined-sewer areas (~60–70% of the city).
- Only 6 usable fluvial USGS gauges fall inside NYC, all on small tributaries
  (drainage area 0.5–38 mi²), with hourly records starting 2007–2010.
- Several sewer/drainage layers are unofficial (Open Sewer Atlas) or not
  recently updated (DEP MS4, last updated 2018).

## Related work

Companion inventories for Philadelphia and Chicago will follow the same structure.

---
*Code and documentation in this repository are licensed under MIT. Underlying datasets are sourced from the providers listed above and remain subject to their original terms*
