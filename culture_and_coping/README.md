# Capstone Project: Culture and Coping

This project analyzes cross-cultural interpersonal risk factors for suicidal ideation using multilevel Bayesian models in R. The models assess the effect of cultural orientation, social connectedness, and psychological variables (e.g., burdensomeness and belongingness) on suicide lifetime prevalence among young adults from Turkey, the US, and Korea.

## Directory Structure

```
culture_and_coping/
├── data/
│   └── data.xlsx                                # Raw dataset
├── Model.R                                      # Main R script (run this)
├── Model1.RData                                 # Saved output of Model 1
├── Model2.RData                                 # Saved output of Model 2
├── LooModelReplication.RData                    # LOO evaluation results
├── WAICModelReplication.RData                   # WAIC evaluation results
├── R2ModelReplication.RData                     # R² statistics
├── Overall_birth_sex.jpeg                       # Visualization: Birth sex
└── Overall_birth_sex_and_marital_status.jpeg    # Visualization: Birth sex + Marital status
```

## Prerequisites

To run this project, ensure you have **R** and **RStudio** installed on your machine.

### Required R Packages
Ensure you have the following R packages installed:
- `brms`
- `rstan`
- `tidyverse`
- `ggplot2`
- `loo`
- `performance`
- `readxl`

You can install them with:

```r
install.packages(c("brms", "rstan", "tidyverse", "ggplot2", "loo", "performance", "readxl"))

### For macOS Users

If you're using macOS, you must install the **Xcode Command Line Tools** to enable C++ compilation for Stan models:

```bash
xcode-select --install




## How to Run
