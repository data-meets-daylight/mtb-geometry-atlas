# Identifying Mountain Bike Categories from Frame Geometry 🚵‍♀️
Year: 2025

_Using only frame geometry to see whether mountain bikes naturally cluster into meaningful categories, and how well those clusters line up with common industry labels._

## Project Overview

This project explores whether medium‑size mountain bikes can be grouped by geometry alone and how those groupings compare with typical labels like Cross‑country, Trail, Enduro and Downhill. We analyse 600+ frames from an open geometry dataset, perform PCA to uncover dominant axes of variation, cluster the bikes, then validate those clusters against suspension‑travel‑based categories. Finally, we train a multi‑class SVM to predict categories from geometry.

## Key Technical Highlights

- PCA on scaled geometry variables reveals two strong axes: a **slack/long geometry** axis and a **rider position** axis.
- **k‑means** on PCs (best‑behaved at _k_ ≈ 6) and **k‑prototypes** on mixed data (_k_ ≈ 3) provide complementary structure.
- Suspension‑travel rules offer an external check: Cross‑country separates cleanly, while Trail/Enduro/Downhill overlap.
- A simple **SVM** achieves ~78% accuracy; most errors occur between neighbouring styles (Trail ↔ Enduro ↔ Downhill).
    

## Features
- End‑to‑end R workflow: cleaning, PCA, clustering, validation, classification.

## Dependencies
- R ≥ 4.2
- Packages: `ggplot2`, `dplyr`, `tidyr`, `patchwork`, `DataExplorer`, `MVN`, `corrplot`, `psych`, `factoextra`, `gridExtra`, `clustMixType`, `cluster`, `ggalluvial`, `e1071`, `ggbiplot`

## How to Run

1. **Clone**
    
    ```bash
    git clone https://github.com/nohat-noplay/stat2004_groupproject.git
    cd stat2004_groupproject
    ```
    
2. **Install packages** (first run only)
    
    ```r
    install.packages(c(
      "ggplot2","dplyr","tidyr","patchwork","DataExplorer","MVN",
      "corrplot","psych","factoextra","gridExtra",
      "clustMixType","cluster","ggalluvial","e1071"
    ))
    ```
    
3. **Data**
    
    - Ensure the MTB geometry CSV exists at `Data/geometrics.mtb-news.de.csv` (semicolon‑separated). If missing, obtain it from the original geometry dataset and place it under `Data/`.

## Supporting Documents
Code folder: For R code and Data
Presentation folder: Powerpoint and Presentation video about our findings (for non-technical audiences)
Report folder: Report on methods and findings 
        
## Credits
Saf Flatters · Timothy Bolt · Lizanne van Nieuwenhuizen

## Connect with Me

📫 [LinkedIn](https://www.linkedin.com/in/safflatters/)

## License and Usage

![Personal Use Only](https://img.shields.io/badge/Personal%20Use-Only-blueviolet?style=for-the-badge)

This project is intended for personal, educational and portfolio purposes only.

You are welcome to view and learn from this work, but you may not copy, modify or submit it as your own for academic, commercial or credit purposes.