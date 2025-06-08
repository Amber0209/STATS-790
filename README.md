# Tomato Experimental Design and Simulation

This repository contains the source code and analysis files for an experiment on tomato growth, with a focus on experimental design and simulation-based model evaluation.

## Contents

- **design.Rmd**  
  This R Markdown file documents the process of constructing, evaluating, and comparing different experimental designs for tomato studies.  
  - Introduces Completely Randomized Designs (CRD), Randomized Complete Block Designs (RCBD), and custom blocking structures (e.g., light, temperature).  
  - Demonstrates code to generate experimental designs under realistic constraints (e.g., number of seeds, treatment levels, blocks).  
  - Computes and compares design optimality criteria (D-, A-, G-optimality) using the generated designs.  
  - Visualizes the relative efficiency of each design to guide the choice of optimal setup for tomato experiments.

- **simulation.Rmd**  
  This R Markdown file presents simulation studies of tomato growth under various conditions, using the optimal designs identified earlier.  
  - Defines a parameter grid over temperature, light, manure levels, and plant type.  
  - Runs tomato growth model simulations for each parameter combination using the `tomgro_single()` function.  
  - Analyzes the impact of key variables (temperature, light, manure, plant type, and duration) on fruit dry weight.  
  - Provides data visualization (scatter plots, smooth trends, heatmaps) to illustrate model responses and insights for experiment planning.

## Getting Started

1. Clone this repository and open it in RStudio.
2. Install required R packages if needed (e.g., `tidyverse`, `ggplot2`, `dplyr`, `MuMIn`).
3. Knit the R Markdown files to generate HTML reports with interactive plots and results.

```r
rmarkdown::render("design.Rmd")
rmarkdown::render("simulation.Rmd")
