# Hand-over: foss4lh Explorer
**Aim:** Modern, high-performance web archive for historical landscape data.
**Stack:** Svelte 5, OpenLayers 10 (`svelte-openlayers`), Bun, Cloudflare R2, GitHub Pages.

## Progress
- **Map:** Integrated `svelte-openlayers` properly (`<View><Map>`).
- **Tiles:** Rotherwas demo connected via relative symlink (`public/tiles/rotherwas`). Fixed TMS `-y` inversion and Vite `404` routing.
- **UI:** Added multi-source picker, text search, and 2-sided date range slider. UI actively filters map layers.
- **Data Ops:** `hfd-data-ops/convert_to_pmtiles.sh` created for GDAL conversions.

## Next Agent Tasks
1. **PMTiles Ingestion:** Process full datasets using the provided GDAL script.
2. **PMTiles Frontend:** Configure OpenLayers to read `.pmtiles` directly.
3. **R2 Deployment:** Upload `.pmtiles` to Cloudflare R2 and configure CORS.
