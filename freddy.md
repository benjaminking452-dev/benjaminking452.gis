# Cyclone Freddy: who lives in the flood's path?

![A3 map sheet showing flood exposure in Mozambique and Malawi](images/freddy-map.png)

[Download the full-resolution A3 map (PDF)](images/freddy-map.pdf)

## The question

How many people in Mozambique and Malawi live in areas at risk of river flooding, and how does that baseline compare with the exposure forecast for Tropical Cyclone Freddy's second Mozambique landfall on 11 March 2023?

This started as a university practical assessment I completed in QGIS. I rebuilt it from scratch in ArcGIS Pro to learn the software, and to make a map I was happy with rather than one shaped by assessment criteria.

## Data

- **Flood hazard:** Fathom Global Flood Map v3 (fluvial, undefended, 1-in-100-year, ~30 m)
- **Population:** WorldPop 2023 constrained counts (~100 m)
- **Boundaries:** geoBoundaries, plus OCHA COD-AB for Malawi's districts after I found errors in the geoBoundaries version
- **Forecast:** GloFAS 51-member ensemble (from earlier coursework)
- **Context:** IBTrACS storm track, Natural Earth rivers, OpenStreetMap places

## Method

1. Mosaicked the flood tiles and classed cells as flooded where depth was 15 cm or more
2. Aggregated the flood layer to the 100 m population grid as a flooded fraction, so no one was double counted, then multiplied by population
3. Summed exposed people per district with zonal statistics
4. Mapped the median of the 51 forecast members, with a box plot showing the spread for the six highest districts
5. Used a 2 km focal sum to find exposure hotspots and choose the three local panels objectively
6. Laid out the sheet in an equal-area projection, with shared scales and class breaks so baseline and forecast can be compared directly

## Key findings

About 1.11 million people live in the 1-in-100-year floodplain across both countries. Seven districts hold 32.5% of them, led by Marromeu on the lower Zambezi.

The main limitations: the flood model ignores flood defences such as the Zambezi's dams, and constrained population data misses people where no buildings were detected. The full methodology covers these.

## What I improved on the original

- **Learned a new tool:** I redid the analysis in ArcGIS Pro and had to make each decision again rather than follow a set practical
- **Tighter method:** a cleaner way of combining the two grid resolutions, plus checks that totals stayed intact
- **More context:** rivers and the storm track make the exposure easier to read
- **Clearer cartography:** consistent colours (blue for water, purple for exposure, red for the storm) and much less visual noise
- **Better workflow:** clearer file naming and project organisation behind the scenes

## Skills and tools

ArcGIS Pro · raster analysis (reclassify, aggregate, raster calculator) · zonal and focal statistics · working with ensemble forecast data · map projections · data quality checking · layout and cartographic design

[← Back to home](./)
