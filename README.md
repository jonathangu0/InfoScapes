# InfoScapes

**Four interactive dashboards for exploring New York City's sanitation, childcare, food access, and drinking water tank inspection data.**

[Explore the live site](https://dataseeds.netlify.app/)

InfoScapes turns NYC Open Data into neighborhood maps, charts, and interactive views. Built with JavaScript, D3.js, Leaflet, and Bootstrap, the application loads and processes data in the browser without a custom backend.

## Dashboards

| Dashboard | What you can explore |
| --- | --- |
| [CleanCityScape](https://dataseeds.netlify.app/src/views/CleanCityScape/index.html) | Sanitation-related 311 complaints, their locations, and historical trends. |
| [KidsCareScape](https://dataseeds.netlify.app/src/views/KidsCareScape/index.html) | Childcare center locations and inspection information, with age-group and borough controls. |
| [NourishWellScape](https://dataseeds.netlify.app/src/views/NourishWellScape/index.html) | Free food distribution locations, contact details, and day-of-week filters. |
| [VivoWaterScape](https://dataseeds.netlify.app/src/views/VivoWaterScape/index.html) | Locations and records from self-reported drinking water tank inspections. |

## Technical Highlights

- **Client-side data processing:** Load CSV and JSON records with D3, parse fields and coordinates, and filter records for visualization.
- **Interactive mapping:** Combine Leaflet maps with D3 SVG overlays to display geographic records and reveal details through tooltips.
- **Geographic context:** Use NYC borough and community district boundary assets, including TopoJSON, to support neighborhood-level exploration.
- **Dashboard interfaces:** Organize maps, charts, and controls using Bootstrap and shared styles, with D3 and NVD3 for visualizations.
- **Static deployment:** Serve HTML, CSS, JavaScript, and data files directly; no application server or database is required.

## Data Sources and Freshness

The core dashboards draw on [NYC Open Data](https://opendata.cityofnewyork.us/):

- NYC 311 Service Requests
- DOHMH Childcare Center Inspections
- HRA Free Food Locations
- Self-Reported Drinking Water Tank Inspection Results

The repository also contains construction-related views and historical reports associated with DOB NOW Build Job Applications.

Data loading varies by view. The sanitation map queries the NYC Open Data API, while childcare, food, and water maps load CSV snapshots committed to the repository. Several bundled files are labeled 2024; the dashboards should not be treated as uniformly current or continuously refreshed. Source coverage, API availability, and snapshot dates affect the records displayed.

## Run Locally

With Git and Python 3 installed:

```bash
git clone https://github.com/jonathangu0/InfoScapes.git
cd InfoScapes
python3 -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000).

Use a local HTTP server rather than opening HTML files directly so browser data requests can resolve. Internet access is needed for externally hosted libraries, map tiles, and API requests. The static site does not require an npm build step; the current `npm start` script only prints a reminder to run a static server.

## Repository Structure

```text
index.html       Landing page linking the four core dashboards
src/views/       Dashboard pages and project background
src/assets/      Shared styles, scripts, fonts, and images
src/data/geo/    Geographic boundary files
src/data/reports/ CSV and JSON datasets and historical reports
src/layouts/     Additional dashboard layouts and construction views
examples/        Dashboard examples and supporting reference material
```

## Background

Created by [Jonathan Guo](https://github.com/jonathangu0), inspired by community service with the NYC Youth Leadership Council and an interest in making public data easier to explore. The project connects frontend development and data visualization with practical questions about neighborhood resources.

The application uses open-source visualization libraries and includes Keen dashboard styles and example material. Existing third-party notices remain with their corresponding files.
