# InfoScapes

InfoScapes is a unified suite of interactive data visualization dashboards designed to analyze and map New York City municipal open data. The application processes high-volume municipal datasets to generate performant geographical layouts and statistical charts.

The primary objective of this project is to implement client-side data wrangling, performant spatial rendering, and interactive dashboard architectures using legacy data visualization frameworks.

## Project Architecture & Core Modules

The application is split into specialized observation layers accessible from a central interface:

* **CleanCityScape:** Parses and maps client-side 311 service request trends, isolating sanitation issues and municipal responsiveness profiles across neighborhoods.
* **KidsCareScape:** Spatial mapping of DOHMH-regulated childcare facilities across the five boroughs to evaluate geographic distribution and capacity.
* **NourishWellScape:** An interactive spatial overview mapping free food distribution nodes, food banks, and localized nutritional emergency resources.
* **VivoWaterScape:** Aggregates and renders self-reported drinking water tank inspection records to audit water safety compliance profiles.
* **Major Construction & Development:** Quantitative breakdowns of Department of Buildings records, tracking outliers in project valuations, building heights, and dwelling unit densities.

## Technical Stack

* **Core Logic & Interface:** HTML5, CSS3, JavaScript (ES6+)
* **UI Architecture:** Bootstrap
* **Data Visualization Engines:** D3.js (v3 spatial bindings), NVD3
* **Mapping & Geospatial Overlays:** Leaflet.js utilizing the `L.D3SvgOverlay` plugin for data-layer bindings.
* **Geospatial Boundaries:** Pre-processed TopoJSON files for optimized, client-side community district and borough line rendering.

## Data Pipelines & Sources

Production pipelines parse assets derived directly from the NYC Open Data portal:
* 311 Service Requests
* DOHMH Childcare Center Inspections
* NYC Human Resources Administration (HRA) Free Food Locations
* DOHMH Self-Reported Drinking Water Tank Inspections
* DOB NOW Build Job Applications