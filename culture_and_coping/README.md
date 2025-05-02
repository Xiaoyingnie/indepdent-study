# Capstone Project: Culture and Coping

This project analyzes cross-cultural interpersonal risk factors for suicidal ideation using multilevel Bayesian models in R. The models assess the effect of cultural orientation, social connectedness, and psychological variables (e.g., burdensomeness and belongingness) on suicide lifetime prevalence among young adults from Turkey, the US, and Korea.

## Directory Structure

├── data/
│ └── data.xlsx # Main dataset used for modeling
├── Model.R # Main R script to preprocess, fit models, and generate plots
├── Model1.RData # Saved fitted Model 1 object
├── Model2.RData # Saved fitted Model 2 object
├── LooModelReplication.RData # LOOIC evaluation results
├── WAICModelReplication.RData # WAIC evaluation results
├── R2ModelReplication.RData # R² values for models
├── Overall_birth_sex.jpeg # Output plot for birth_sex
├── Overall_birth_sex_and_marital_status.jpeg # Output plot for interaction effects
