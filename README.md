# AGAIF_CA3_InteractiveMap

Certified Assessment 3, AGAIF 2026 Bootcamp 1: AI-Assisted Interactive Web Mapping Using Leaflet.js

## What's in this folder

```
index.html              Main web page
styles.css                Styling for the layout, sidebar, legend and pop-ups
script.js                Leaflet.js logic: base map, data loading, layers, pop-ups
data/
  boundary_data.js          10 ASEAN country boundary polygons (converted from the
                             provided Asean.shp, reprojected from Web Mercator to WGS84)
  places_data.js             230 place points (converted from the provided Place.shp,
                             already in WGS84)
CA3_Report.pdf           Written report: AI tool/prompts used, source code, corrections
                         modifications or improvements, screenshots, brief explanation on
                         development, testing and troubleshooting
screenshots/             Screenshots of the completed map (also embedded in the PDF report)
README.md                This file
```

## How to open the application

Because the app loads the two GeoJSON files with JavaScript's `fetch()`, most browsers
will **block this if you just double-click `index.html`** (opening it as a `file://`
path triggers a CORS restriction). Instead, serve the folder over a local HTTP server:

**Option A — Python (built into most systems):**
```bash
cd path/to/this/folder
python3 -m http.server 8000
```
Then open **http://localhost:8000/index.html** in your browser.

**Option B — VS Code:**
Install the "Live Server" extension, right-click `index.html`, and choose
"Open with Live Server."

**Option C — Node.js:**
```bash
npx serve .
```

## What the map does

- Displays an OpenStreetMap base map with full zoom/pan.
- Loads and displays the 10 ASEAN country boundaries, each coloured individually,
  with a hover highlight and a click pop-up showing the country name and reference link.
- Loads and displays all 230 places as circle markers, coloured by place type
  (city / county / country) and sized by reported population, each with a click
  pop-up showing name, country, type, population and coordinates.
- Sidebar checkboxes let you toggle the country layer and the place layer independently.
- A legend explains the place-type colour coding.
- The map automatically zooms/pans to fit the full extent of the loaded data on startup.
- Attribution for Leaflet.js, OpenStreetMap, and the source dataset is shown in the
  page footer.

## Data source

Provided dataset: `ASEAN_Shp_Data.zip` (Asean.shp country boundaries, Place.shp point
locations, and an accompanying Place.xlsx reference table), supplied as part of
Certified Assessment 3.
