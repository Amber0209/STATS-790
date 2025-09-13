# Tomato Experimental Design and Simulation

This repository contains the source code and analysis files for studying tomato growth, with a focus on **experimental design, simulation-based evaluation, and automated feedback generation**.

## Contents

### **State_variable.Rmd**
This R Markdown file demonstrates a single-run simulation of tomato growth using the `tomgro_single()` function from `tomgro.r`.  
- Defines environmental inputs including mean temperature, light intensity (PPFD), fertilizer composition, and plant type.  
- Simulates the 90-day growth cycle of tomato plants under these conditions.  
- Tracks the dynamics of key state variables: total biomass (W), fruit biomass (Wf), stem biomass (Wm), leaf area index (LAI), and node number (N).  
- Produces a multi-panel line plot to visualise trajectories of all variables across time, with independent scaling for clearer interpretation.  

### **simulation.Rmd**
This R Markdown file presents simulation studies of tomato growth under various conditions, using the optimal designs identified earlier.  
- Defines a parameter grid over temperature, light, manure levels, and plant type.  
- Runs tomato growth model simulations for each parameter combination using the `tomgro_single()` function.  
- Analyzes the impact of key variables (temperature, light, manure, plant type, and duration) on fruit dry weight.  
- Provides data visualisation (scatter plots, smoothed trends, heatmaps) to illustrate model responses and insights for experiment planning.  

### **design.Rmd**
This R Markdown file documents the process of constructing, evaluating, and comparing different experimental designs for tomato studies.  
- Introduces Completely Randomized Designs (CRD), Randomized Complete Block Designs (RCBD), and custom blocking structures (e.g., light, temperature).  
- Demonstrates code to generate experimental designs under realistic constraints (e.g., number of seeds, treatment levels, blocks).  
- Computes and compares design optimality criteria (D-, A-, G-optimality) using the generated designs.  
- Visualises the relative efficiency of each design to guide the choice of optimal setup for tomato experiments.  
- Includes analysis of **thrived** (high-yield) and **survived** (minimum-yield) manure ranges, comparing mean efficiencies of designs that fall fully within these biological thresholds against those that do not. This highlights the trade-off between focusing treatments in biologically attractive regions and maintaining statistical efficiency for parameter estimation.  

### **Suggestion.Rmd**
This R Markdown file documents the process of generating feedback for student experimental designs by comparing them against gold standard benchmarks.  
- Implements functions to compute and compare D-, A-, and G-optimality at both global and parameter-specific levels.  
- Identifies weaknesses such as limited treatment coverage or isolated plots through variance ratio and prediction diagnostics.  
- Translates diagnostic results into **student-friendly suggestions**, linking statistical efficiency losses to concrete greenhouse factors (fertilizer, temperature, light, plant type).  
- Demonstrates the end-to-end feedback pipeline, from input design to optimality computation and final suggestions, with flowcharts and worked examples.  

## Getting Started

1. Clone this repository and open it in RStudio.  
2. Install required R packages if needed (e.g., `tidyverse`, `ggplot2`, `dplyr`, `MuMIn`).  
3. Knit the R Markdown files to generate HTML reports with interactive plots and results.  

---

## Getting Started

1. Clone this repository and open it in RStudio.
2. Install required R packages if needed (e.g., `tidyverse`, `ggplot2`, `dplyr`, `MuMIn`).
3. Knit the R Markdown files to generate HTML reports with interactive plots and results.
