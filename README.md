# Epiphytic foraminifera assemblage drivers in Recife das Pinaunas, Brazil

This repository contains the data analysis and code supporting the paper:  
**“Epiphytic foraminifera assemblage drivers in Recife das Pinaunas, Brazil”**

This study investigates the spatial and seasonal variation in the assemblages of Epiphytic Foraminifera

---

## Repository Structure

```text
├── data/
│   ├── table_S3_environmental_variables.pdf    # Environmental variables (pH, salinity, DO, etc.)
│   ├── table_S2_epiphytic_foram_abundance_data.pdf     # Species abundance matrix
│
├── results/
│   ├── statistical_analysis                    # Statistical summaries, ANOVA, PERMANOVA, VIF, GAM outputs
│   ├── plots                                   # Visualization panels (diversity, environmental, NMDS, GAM)
│
├── epiphytic_foram_env_analyses.R # Main R analysis script
│
└── README.md                                   # Repository documentation
```

---

## Workflow Overview

The main script **`epiphytic_foram_env_analyses.R`** performs the following analytical workflow:

1. **Data Import and Cleaning**  
   Loads and merges environmental and community datasets for 15 sampling sites.

2. **Diversity Analyses**  
   Calculates and compares:
   - Shannon–Wiener diversity
   - FoRAM Index
   - Margalef richness
   - Pielou’s evenness  
   across seasons and river basins.

3. **Community Composition**  
   - Tests assemblage differences using **PERMANOVA** (Bray-Curtis dissimilarity).  
   - Visualizes results via **NMDS** ordination with 95% confidence ellipses.

4. **Environmental–Diversity Relationships**  
   - Linear regression models for the environmental available variables.

5. **Species Contribution (SIMPER)**  
   - Identifies top 10 taxa contributing most to spatial and seasonal dissimilarities in assemblage composition.

---

## R Packages Used

| Package | Functionality |
|----------|----------------|
| **dplyr**, **tidyr**, **reshape2** | Data cleaning and transformation |
| **ggplot2**, **cowplot** | Visualization and figure arrangement |
| **car** | Variance Inflation Factor (VIF) analysis and statistical tests |
| **vegan** | Ecological and multivariate analyses (PERMANOVA, NMDS, dbRDA, SIMPER, diversity) |

---

## Reproducibility

All analyses were conducted in **R version 4.5.1**.

To reproduce the workflow:

```r
# Set working directory to repository root
setwd("path/to/epiphytic_foraminifera_assemblages/")

# Run analysis
source("epiphytic_foram_env_analyses.R")
