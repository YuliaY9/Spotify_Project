## Predicting Spotify Track Popularity
This project aims to predict the popularity score (0–100) of Spotify tracks based on both **audio features** and **playlist exposure metrics**.
The goal is to explore whether a song’s **sound** or its **exposure** (artist, playlist, album) better explains its success.

# Research Question & Goal
**Research Question:**  
What makes a Spotify track popular — its sound or its exposure?

**Goal:**  
Build a regression model to predict track popularity using audio and playlist metadata.

# Dataset
- **Source:** Kaggle - Spotify Songs Dataset  
- **Size:** 32,833 tracks  
- **Features:** 23 initial features (audio + metadata)

# Workflow Overview
1. **Data Preparation:** Import & organize raw dataset  
2. **EDA:** Explore data distributions and correlations  
3. **Cleansing:** Handle outliers (IQR) and missing values (MICE)  
4. **Feature Engineering:** Create new features (keywords, exposure counts, temporal variables)  
5. **Feature Selection & Modeling:**  
   - Compared One-Hot Encoding, Target Encoding, and Hybrid  
   - Best model: **XGBoost (Target Encoding set)**  
   - Performance:  
     - DEV R² = 0.56  
     - TEST R² = 0.55

# Key Insights
- **Playlist & artist exposure** predict popularity better than audio features.  
- **Audio traits** (like energy & loudness) still contribute secondary signals.  
- Model explains **~55% of variance** in popularity (moderate accuracy).  

**Applications:**  
Can support playlist creation, marketing prioritization, and artist & repertoire (A&R) decisions.

Model interpretation was conducted using SHAP to visualize and explain feature impacts on Spotify track popularity.

# Repository Structure
Spotify_Project/
│
├── 1_Prep/ # Data preparation scripts
├── 2_EDA/ # Exploratory Data Analysis (incl. Sweetviz report)
├── 3_Cleansing/ # Outlier handling & imputation
├── 4_Feature_Engineering/ # Feature creation
├── 5_Data_Selection/ # Feature selection results
├── 6_Modeling/ # Model training and tuning
├── 7_SHAP_Analysis/       # Model interpretability and feature impact visualization
└── Documentation_Spotify.docx # Project summary


# How to Run
1. Clone this repository  
2. Open any `.ipynb` file in **Google Colab**  
3. Run the notebook sequentially from `1_Prep` → `6_Modeling`  

# Notes on Large or Non-Displayable Files
Some project outputs cannot be previewed directly on GitHub due to file size or format limitations: 
for example: `spotify_sweetviz.html` — Automated EDA report (~60 MB).  
  **How to view:** Click “View raw” → Download → Open locally in your browser.
- `.pkl` files — Machine learning model and dataset pickles.  
  These files must be loaded using Python (e.g., `pickle.load()`).
- Large `.csv` files — GitHub may show only a partial preview;  
  download to view full data.
- Other `.html` reports (if any) — Same process: download and open locally.

All files are safely stored in the repository and can be accessed by downloading them.

**Yulia Yaron**  
November 2025  
Machine Learning Capstone Project – Spotify Track Popularity Prediction
