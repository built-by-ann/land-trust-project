# 🗺️ Predicting Land Conversion in Tennessee: A Spatiotemporal Approach Using ConvLSTM

**Authors**: Ann Mathew, Manda Li, Isaac Liu, Steven Yi, Teo Kitanovski   
**Team Members**: Manda Li (Team Lead), Isaac Liu, Steven Yi, Teo Kitanovski  
**Tools used**: QGIS, Rasterio, PyTorch  
**Vanderbilt Data Science 2024**

---

## 📌 Introduction

Urban and suburban expansion pose serious challenges to land conservation. In collaboration with the Land Trust of Tennessee, this project forecasts future land cover changes across Tennessee using remote sensing and deep learning.

By leveraging the spatiotemporal strengths of ConvLSTM, we aim to answer:
1. Where are natural and agricultural lands most at risk of development?
2. How can temporal trends in past land cover inform future predictions?
3. What insights can we provide to guide conservation efforts statewide?

---

## 🛰️ Methods

We used:
- **NLCD Land Cover Data (2001–2021)** – raster data at 30m resolution  
- **Classes 21–24** as the target "developed" categories  
- **Tennessee boundary shapefile** to define the study region

Steps:
- Extracted 64×64 raster patches using `rasterio`, filtered with 2D prefix sums to include dynamic regions only  
- Trained a **ConvLSTM model** to capture both spatial and temporal changes  
- Applied the model to generate future prediction maps (2030, 2040, 2050)  
- Aggregated overlapping patches for smooth and continuous outputs  
- Visualized results and comparisons using QGIS

---

## 📊 Results

- **Land development risk** was highest around urban cores and transport corridors.
- **Prediction maps** clearly show expansion patterns from 2021 to 2050.
- Model outputs suggest notable conversion pressure on farmland in Middle Tennessee.

---

## 💬 Discussion

The project validates **ConvLSTM** as a strong model for geospatial change detection, combining sequence learning with raster image structure. Challenges included:
- High memory load during raster-to-vector conversions  
- Limited auxiliary features (e.g., slope, floodplain) in early model versions  
- Difficulty managing large, multi-band geotiff files across temporal spans

---

## 🌱 Future Work

- Add geographic and demographic layers (e.g., population growth, infrastructure proximity)  
- Improve resolution and frequency of time steps using additional NLCD years  
- Develop an interactive dashboard for conservation stakeholders

---

## 📂 Files in this Repo

- [`poster/landtrust-poster.pdf`](poster/landtrust-poster.pdf) – final presentation poster

![`poster/landtrust-poster.pdf`](poster/landtrust-poster.pdf) – final presentation poster
