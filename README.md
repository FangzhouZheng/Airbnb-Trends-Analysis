# Airbnb Price Trends & Superhost Patterns: Los Angeles vs. New York City

## Project Overview

This academic team project compares Airbnb listing characteristics in **Los Angeles (LA)** and **New York City (NYC)**. Using Python, exploratory data analysis, statistical modeling, machine learning, and geospatial visualization, we investigate how listing prices vary across the two markets and which property and host attributes are associated with **Superhost status**.

### Research Questions

- How do listing prices and price distributions differ between LA and NYC?
- Which listing characteristics are associated with higher or lower prices?
- How do Superhost patterns and associated features compare across the two cities?
- How do property types, room types, amenities, and geographic distributions differ?

## Dataset

The analysis uses Airbnb listing data for Los Angeles and New York City, with additional data referenced for selected comparisons and validation steps. The notebook identifies **Inside Airbnb** and **Kaggle** as data sources.

| Dataset | Original listings | Listings after cleaning |
|---|---:|---:|
| Los Angeles | 45,591 | 21,120 |
| New York City | 39,627 | 12,966 |
| **Total** | **85,218** | **34,086** |

The original city datasets each contain **75 columns**; the cleaned datasets retain **29 columns**. The substantial reduction in observations is important when interpreting the results.

### Example Variables

- Listing price and room/property type
- Number of guests accommodated, beds, and bathrooms
- Host response rate and Superhost status
- Reviews and review scores
- Availability and minimum-night requirements
- Neighborhood and geographic coordinates
- Listed amenities

> **Data note:** The notebook uses complete-case deletion (`dropna(how='any')`) during cleaning. This removes many observations and may introduce selection bias if missingness is not random.

## Tools & Technologies

- **Python:** Pandas, NumPy
- **Exploratory analysis and visualization:** Matplotlib, Seaborn
- **Statistical modeling and machine learning:** Scikit-learn
- **Geospatial visualization:** Folium
- **Environment:** Jupyter Notebook / Google Colab

## Methodology

### 1. Data Cleaning & Feature Engineering

- Selected relevant listing and host attributes from the raw city datasets.
- Removed records with missing values and checked for duplicate listing/host identifiers.
- Converted price strings into numeric values and response-rate percentages into numeric fields.
- Encoded selected Boolean variables, including Superhost and instant-booking indicators.
- Extracted numeric bathroom counts from text descriptions.
- Created an average-availability feature from several availability windows.
- Prepared categorical features for modeling using dummy-variable encoding.

### 2. Exploratory Data Analysis

Compared the two cities across:

- Listing price ranges, distributions, and extreme outliers
- Neighborhood-level geographic patterns
- Room types and property types
- Review scores and availability
- Common amenities and listing characteristics
- Superhost proportions

### 3. Price Modeling

Explored associations between listing characteristics and prices using:

- Correlation analysis
- Simple and multiple linear regression
- Decision-tree-based analysis

The notebook reports an **R² of approximately 0.357** for a multivariable linear regression specification. This indicates that substantial variation in prices remains unexplained by the included features; it is not evidence of strong predictive performance.

### 4. Superhost Analysis

Used a **Random Forest classifier** to examine feature importance associated with Superhost status in each city. The analysis compares how the relative importance of host and listing attributes differs between LA and NYC.

Feature importance should be interpreted as a model-based association, **not** a causal effect or an official description of Airbnb's Superhost eligibility criteria.

### 5. Geographic Visualization

Used **Folium** to visualize spatial patterns in listing prices and room types, supporting side-by-side interpretation of the two markets.

## Key Findings

### Pricing Differences

- **Los Angeles** exhibited a wider price distribution and more pronounced high-price outliers in the analyzed listings.
- **New York City** showed a comparatively more concentrated price distribution.
- Extreme listing prices can strongly influence averages and visual scales, so comparisons require care.

### Factors Associated With Price

Regression and decision-tree analyses suggest that pricing relationships vary by market and listing characteristics. The multivariable linear regression result (**R² ≈ 0.357**) also highlights the limitations of explaining prices using the selected features alone.

### Superhost Patterns

The notebook identifies differences in Superhost proportions and model-based feature rankings between LA and NYC. These are descriptive and predictive associations, rather than causal conclusions.

### Property Types & Amenities

The analysis compares room-type distributions and common amenities across the two cities, including Wi-Fi, kitchens, and safety-related features. These comparisons provide additional context for interpreting market differences.

## Project Deliverables

- Cleaned and transformed Airbnb listing data for two cities
- Exploratory charts and cross-city comparisons
- Linear regression and decision-tree analyses of price
- Random Forest feature-importance analysis for Superhost status
- Folium-based geographic visualizations
- A consolidated Jupyter Notebook containing the analysis and discussion

## Limitations & Future Improvements

1. **Missing-data bias:** Complete-case deletion substantially reduced the sample. Future work should compare missingness patterns and test alternative imputation strategies.
2. **Outlier sensitivity:** Extremely high listing prices may distort summary statistics and regression estimates. Robust methods or carefully justified transformations could help.
3. **Observational data:** Correlations and feature importances do not establish causality.
4. **Model validation:** Further work should use clearly separated training and test data, cross-validation, and appropriate error metrics for price prediction and Superhost classification.
5. **Temporal interpretation:** Listing snapshots and auxiliary datasets should not automatically be treated as verified transaction or booking histories.
6. **Reproducibility:** Input data paths in the notebook reference a Colab environment. To rerun the project, download the relevant datasets and update the file paths.

## Repository Structure

```text
Airbnb-LA-NYC-Analysis/
├── README.md
└── B03_Analyzing_Airbnb_Price_Trends_&_Super_Host_Patterns_between_LA_and_NYC.ipynb
```

> Rename the notebook in this example if you use a different filename in your repository. Raw datasets are not included in this proposed structure.

## How to Run

1. Clone or download this repository.
2. Install the Python packages used in the notebook (including `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, and `folium`).
3. Obtain the relevant Airbnb datasets from the sources documented in the notebook.
4. Update the notebook's local or Colab file paths to point to your downloaded data.
5. Run the notebook cells in order and review the generated visualizations and model outputs.

## Project Information

**Project type:** Academic team project  
**Institution:** Boston University  
**Focus:** Business Analytics, Exploratory Data Analysis, Regression, Machine Learning, Geospatial Visualization

### Team

Yu (Kathy) Xu · Ruoxian (Roxy) Zhang · Fangzhou (Franco) Zheng · Manan Goel · Zicheng Wang

## Acknowledgments

The original notebook includes a generative AI disclosure and a references section. Please retain the original project acknowledgments and any required attribution when publishing the repository.
