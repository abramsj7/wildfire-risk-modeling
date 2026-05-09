# Wildfire Risk Modeling

Spatial machine learning project analyzing NASA satellite wildfire detections to classify wildfire intensity and evaluate the impact of spatial features on model performance.

---

# Project Overview

This project explores whether satellite wildfire observations can be used to classify wildfire intensity and whether incorporating spatial relationships between nearby wildfire detections improves model performance.

The analysis combines machine learning and spatial statistics to evaluate wildfire detection data across the contiguous United States.

A baseline Random Forest model is compared with a spatially informed model that incorporates information from neighboring wildfire detections.

---

# Research Question

Can satellite observations be used to classify wildfire intensity, and does incorporating spatial relationships between nearby fires improve model performance?

---

# Dataset

The dataset used in this project is derived from **NASA VIIRS satellite wildfire detection data**.

Key variables used in the analysis include:

- **bright_ti4** — brightness temperature of the fire (Kelvin)
- **frp** — Fire Radiative Power (energy released by the fire)
- **scan** — satellite pixel width
- **track** — satellite pixel height
- **latitude / longitude** — geographic coordinates of wildfire detections

A binary classification label is created:

- **high_fire = 0** → lower intensity fire  
- **high_fire = 1** → higher intensity fire

The dataset is filtered to include only the contiguous United States (CONUS).

---

# Repository Structure

After cloning the repository, the folder structure should look like this:

```
wildfire-risk-modeling/
│
├── wildfire_detection.ipynb
├── fires.csv
└── README.md
```

---

# How to Run This Project

### Step 1 — Clone the Repository

```
git clone https://github.com/abramsj7/wildfire-risk-modeling.git
cd wildfire-risk-modeling
```

---

### Step 2 — Install Required Libraries

Install the required Python libraries:

```
pip install pandas numpy matplotlib seaborn scikit-learn geopandas libpysal esda
```

---

### Step 3 — Launch the Notebook

Start Jupyter Notebook or Jupyter Lab:

```
jupyter lab
```

Then open:

```
wildfire_detection.ipynb
```

Run the notebook cells from top to bottom to reproduce the analysis and results.

---

# Methods

The analysis follows the following workflow:

1. Data loading and preprocessing  
2. Geographic filtering for the contiguous United States  
3. Exploratory spatial visualization  
4. Correlation analysis of wildfire variables  
5. Baseline Random Forest classification model  
6. Identification and correction of data leakage  
7. Spatial autocorrelation testing using **Moran’s I**  
8. Spatial feature engineering using neighboring wildfire detections  
9. Spatial machine learning model  
10. Model performance comparison  

---

# Key Findings

- Wildfire detections exhibit strong spatial clustering across the United States.
- The initial baseline model revealed a data leakage issue, which was corrected.
- Incorporating spatial information improved classification accuracy from approximately 0.78 to 0.82.

These results demonstrate that spatial relationships between wildfire detections contain meaningful predictive information that can improve machine learning models.

---

# Reproducibility

This project is fully reproducible using the provided dataset and notebook. Running the notebook from top to bottom will reproduce all figures, spatial analyses, and machine learning results.
