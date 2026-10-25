# Calcite WebGIS Shell

A WebGIS front-end prototype built with **Calcite Components** and the **ArcGIS Maps SDK for JavaScript**.
It provides a full-screen application shell (header, collapsible left/right panels with action bars)
and a map in the main content area. The header is laid out **right-to-left (RTL)** for Persian users.

## Features

- Full-height `calcite-shell` layout
- RTL navigation header with logo/user area (`calcite-navigation`, `calcite-navigation-user`) and a refresh menu item
- Left panel (`panel-start`) with an action bar: Save, Map, Layer
- Right panel (`panel-end`) with an action bar: Layer, Styles, Filter, Configure
- Panels expand/collapse and update their heading when an action is clicked
- ArcGIS `MapView` with the `topo` basemap in the main content area
- Plain HTML + JavaScript, no build step

## Tech stack

| Library | Version |
|---|---|
| [Calcite Components](https://developers.arcgis.com/calcite-design-system/) | 2.13.0 |
| [ArcGIS Maps SDK for JavaScript](https://developers.arcgis.com/javascript/latest/) | 4.30 (AMD) |

Both are loaded from the Esri CDN (`js.arcgis.com`).

## Project structure

```
.
├── index.html     # Shell layout, map and panel logic
├── Amard.png      # Organization logo (header)
└── Mohammad.png   # User thumbnail (header)
```

## Usage

1. Clone the repository.
2. Put your own images next to `index.html` (or change the `thumbnail` paths).
3. Serve the folder with any static web server, e.g.:
   ```bash
   python -m http.server 8080
   ```
4. Open `http://localhost:8080` in a browser (internet access is required for the CDN).

## Customization

- **Basemap / start view:** change `basemap`, `center` and `zoom` in the `Map` / `MapView` setup.
- **Panels & actions:** add or edit `calcite-action` items inside `calcite-action-bar`; the click
  handlers at the bottom of the page toggle the panel and set its heading from the action's `text`.
- **User / header text:** edit the `full-name` and `username` attributes of `calcite-navigation-user`.
- **Direction:** remove `direction: rtl` from `calcite-navigation` for a left-to-right layout.

## Roadmap ideas

- Layer list, legend and basemap gallery inside the left panel
- Style / filter / popup configuration in the right panel
- Load web maps or feature services from ArcGIS Online / ArcGIS Enterprise

## License

MIT (or your preferred license)
