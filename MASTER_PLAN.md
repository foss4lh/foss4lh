# David Lovelace Archive (foss4lh)

This project is dedicated to archiving, digitizing, and sharing over 30 years of landscape history and nature conservation data for Herefordshire, collected by David Lovelace.

## Next Agent Task: Process and Catalog the David Lovelace Landscape Archive

### 1. Initial Setup
Start by creating a workspace and cloning the core repositories from the `foss4lh` organization:
```bash
mkdir -p ~/github/foss4lh && cd ~/github/foss4lh
gh repo clone foss4lh/foss4lh
gh repo clone foss4lh/hfd-landscape-explorer
gh repo clone foss4lh/hfd-data-ops
gh repo clone foss4lh/hfd-public-records-office
gh repo clone foss4lh/hfd-tithe-surveys
gh repo clone foss4lh/hfd-aerial-photography
gh repo clone foss4lh/hfd-nature-surveys
```

### 2. Strategic Orientation
Read **`foss4lh/foss4lh/MASTER_PLAN.md`** and **`foss4lh/foss4lh/datasets.csv`** to understand the archive's scope and the target repository for each data type.

### 3. Data Discovery & Delegation (External Drive)
The raw data (approx. 4TB), including **`Habitat.zip`** and the primary archive folders, is located on the external disk at:
**`/run/media/robin/foss4lh/david-lovelace-archive/`**

For each dataset listed in `datasets.csv`, **delegate to a specialized sub-agent** the following tasks:
- **Search:** Locate the corresponding folders on the external disc (e.g., `Maps/`, `AirPhotos/`, `History/`).
- **Catalog:** Create a file list and metadata summary for that specific dataset within its corresponding `hfd-*` repo.

### 4. Critical Task: Efficient Compression & Conversion
The archive contains hundreds of GBs of `.tiff`, `.acw`, and Sony Raw (`.arw`) files. **GitHub and static web hosting cannot handle these raw formats directly.** 
- **Mandate:** You MUST prioritize converting large rasters into web-native, compressed, and "streamable" formats.
- **Formats:** Convert `.tiff`/`.acw` to **Cloud-Optimized GeoTIFFs (COG)** or **PMTiles** using GDAL and the `pmtiles` CLI.
- **Tooling:** Reference the templates in the **`hfd-data-ops`** repository for automation scripts.

### 5. Technical Target
The end goal is to serve these compressed datasets via the **`hfd-landscape-explorer`** (Svelte 5 / OpenLayers 10) web app, pointing to assets hosted on **Cloudflare R2** to enable zero-egress, high-performance browsing of the 30-year collection.
