# 🛰️ GeoAI Sentinel-2 Land Cover & Forest Loss Classifier (2017–2023)

An end-to-end Geospatial Machine Learning pipeline built on **Google Earth Engine (GEE)** using **Sentinel-2 10m Multispectral Surface Reflectance** and **Random Forest Classification** to map land cover and detect forest loss.

## 📌 Features
- **Cloud Masking:** Uses Sentinel-2 Scene Classification Layer (`SCL`) to remove cloud & shadows.
- **Feature Engineering:** Computes NDVI, MNDWI, and NBR spectral indices.
- **Reference Ground Truth:** Stratified sampling based on **ESA WorldCover v200 (10m)**.
- **Machine Learning:** 100-tree Smile Random Forest Classifier.
- **Disturbance Analysis:** Dual-season composite comparison (2017 vs 2023) using $\Delta\text{NBR}$ masked by baseline tree canopy.

## 📊 Model Architecture & Data Flow
1. **Inputs:** Sentinel-2 SR Harmonized (`B2`, `B3`, `B4`, `B8`, `B11`) + Indices (`NDVI`, `MNDWI`, `NBR`)
2. **Train/Test Split:** 80% Training / 20% Testing (Stratified Random Sampling)
3. **Accuracy Metrics:** Confusion Matrix, Overall Accuracy, Kappa Coefficient

## 🚀 Quickstart
1. Open the [Google Earth Engine Code Editor](https://code.earthengine.google.com/).
2. Define or import your Area of Interest polygon as `table`.
3. Paste the contents of `classifier.js` and click **Run**.

## 🛠️ Tech Stack
- Google Earth Engine (GEE API)
- Sentinel-2 Level-2A (COPERNICUS/S2_SR_HARMONIZED)
- ESA WorldCover v200
- JavaScript / Python (Geemap)
