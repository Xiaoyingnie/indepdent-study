# Culture and Coping

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
```

### For macOS Users

If you're using macOS, you must install the **Xcode Command Line Tools** to enable C++ compilation for Stan models:

```bash
xcode-select --install
```
## How to Run
Follow these steps to run the project from start to finish:

### 1. Open the Project in RStudio
- Open the R project file
- Or, open the script `Model.R` Directly
### 2. Set the Working Directory
Open RStudio, and set the working directory to the project folder (where `Model.R` is located):

```r
setwd("/path/to/your/project/folder")
```
### 3. Run the Script

Run the main script to perform the full analysis:

```r
source("Model.R")
```

This script will:

- Load and clean the dataset from data/data.xlsx

- Fit two Bayesian multilevel models using brms

- Save model outputs: Model1.RData, Model2.RData

- Compute model evaluation metrics: LOO, WAIC, R²

- Generate and save result visualizations in .jpeg format

### 4. View Results
After the script completes:
- **Model outputs** are saved as `.RData` files:
  - `Model1.RData`
  - `Model2.RData`

- **Evaluation metrics** are saved in:
  - `LooModelReplication.RData`
  - `WAICModelReplication.RData`
  - `R2ModelReplication.RData`
 

- **Visualizations** can be found as:
  - `Overall_birth_sex.jpeg`
  - `Overall_birth_sex_and_marital_status.jpeg`

## Done
All results will be available in working directory.

## Note on Runtime Performance

Running the full script using `source("Model.R")` may take significantly longer than executing it line by line in the R console. This is expected behavior due to the following reasons:

1. **Model Compilation Overhead**  
   Each time you run a `brm()` model, Stan compiles it into C++ code. This compilation can take 15–30+ seconds per model on macOS.  
   When running the code line by line, the compiled model is retained in memory, which reduces redundant compilation time.

2. **Lack of Intermediate Feedback**  
   Using `source()` runs the entire script at once, so you won’t see any progress or partial output until it finishes.  
   Running the script interactively provides real-time updates and better visibility into each step.

3. **Stacked Computation Without Pauses**  
   The script performs multiple heavy operations in a row (model fitting, LOO/WAIC evaluation, plotting).  
   This consumes more CPU and memory in one go compared to manual step-by-step execution.

4. **No Opportunity to Interrupt or Debug Early**  
   If something goes wrong during model fitting (e.g., divergent transitions), you won’t notice until the end.  
   Running it line by line allows early inspection and debugging.


