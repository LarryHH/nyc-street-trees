# A city of trees

An interactive 3D map of **every street tree in New York City**. Each block is
drawn as a green tower whose height and colour show how many trees grow there.

**Live site:** https://larryhh.github.io/nyc-street-trees/

Drag to pan, scroll to zoom, and use the **Orbit** button to tilt and spin the
city. Hover a tower to see how many trees are in that block. The panel on the
left summarises the whole dataset: trees per borough, tree health, the most
common species, and roughly one street tree for every few dozen New Yorkers.

This is a teaching example for **CITS1501** at UWA, used in the data
visualisation lab to show what a real dataset looks like when it is turned into
a picture you can explore.

## What's in here

| File | What it is |
| --- | --- |
| `index.html` | The page itself: layout, styling, and the code that builds the map. |
| `trees_data.js` | One `[longitude, latitude]` pair for each of the 683,788 trees. |
| `city_extras.js` | Summary numbers for the panel, plus the borough and city outlines. |

The map is built with [deck.gl](https://deck.gl), a library for drawing large
datasets on a map in the browser. It is loaded from a public CDN, so there is
nothing to install.

## Running it on your own computer

Because the page loads the two data files, opening `index.html` directly with a
double-click may not work (browsers block file-to-file loading for security).
Serve the folder over a tiny local web server instead:

```
cd nyc-street-trees
python3 -m http.server 8000
```

Then open <http://localhost:8000> in your browser. Press `Ctrl + C` in the
terminal to stop the server when you are done.

## Data and credits

- Tree data: [NYC Street Tree Census, 2015](https://data.cityofnewyork.us/Environment/2015-Street-Tree-Census-Tree-Data/uvpi-gqnh),
  published by the NYC Department of Parks and Recreation on NYC Open Data.
- Basemap tiles: Esri "Dark Gray Canvas" (World Dark Gray Base). Esri asks that
  the basemap be credited as: Esri, HERE, Garmin,
  [© OpenStreetMap contributors](https://www.openstreetmap.org/copyright), and
  the GIS user community.
- Rendering: [deck.gl](https://deck.gl), MIT licensed.

These credits are also shown on the page itself, along the bottom edge, which is
where the Esri basemap attribution is required to appear.

The population figure used for the per-capita fact is the New York City census
estimate for the same period.
