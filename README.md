# urban-floods-map-assets

# World Bank Official Boundaries - Web Optimized (GeoJSON)

This repository hosts web-optimized GeoJSON files for the World Bank Official Boundaries, intended for use in MapLibre/Mapbox scrollytelling and immersive web features.

## Data Source
The original datasets were sourced from the [World Bank Data Catalog](https://datacatalog.worldbank.org/search/dataset/0038272/world-bank-official-boundaries). 
* `Admin 0`: International boundaries.
* `NDLSA`: Non-Demarcated Lines and Sensitive Areas.

## Optimization Note
To ensure high performance and mobile accessibility for web-based interactive maps, the `Admin_0.geojson` file in this repository has been geometrically simplified using [Mapshaper](https://mapshaper.org/). 

* **Methodology:** The file was simplified by reducing the vertex count (approx. 5-10% retention) while strictly preserving polygon topology and preventing shape removal. This reduces the file size significantly, preventing browser crashes on mobile devices during scroll-triggered map animations.
* **Compliance:** The `NDLSA.geojson` file **has not been simplified or altered** in any way, ensuring that the exact geometry of all sensitive and disputed borders remains 100% faithful to the official World Bank Cartography guidelines. 

## Usage
When implementing these files in web maps, ensure that the `NDLSA` layer is drawn *above* the `Admin 0` layer and styled with a dashed line array (e.g., `[3, 3]`), per World Bank cartographic standards.
