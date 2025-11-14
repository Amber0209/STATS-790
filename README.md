# Tomato Experimental Design and Simulation

This repository contains the source code and analysis files for studying tomato growth, with a focus on **experimental design, simulation-based evaluation, and automated feedback generation**.

## Contents

### **tomgro.Rmd**
This R Markdown file implements a reduced tomato growth model adapted from Jones (1991, 1999).
- The core physiological functions (node initiation, LAI expansion, biomass and fruit growth) were provided by the supervisor.
- The model simulates daily temperature and PPFD to produce plant, fruit, and mature fruit dry weights across a 90-day cycle.
- The file is used to generate plots that illustrate growth trajectories and environmental responses.
- The tomgro() function applies the model to full 7×7 greenhouse designs, producing results for all plots.
- The tomgro_single() function (written by me) provides a simplified wrapper for simulating a single plant under mean environmental conditions and a chosen manure level.

### **State_variable.Rmd**
This R Markdown file demonstrates a single-run simulation of tomato growth using the `tomgro_single()` function from `tomgro.r`.  
- Defines environmental inputs including mean temperature, light intensity (PPFD), fertilizer composition, and plant type.  
- Simulates the 90-day growth cycle of tomato plants under these conditions.  
- Tracks the dynamics of key state variables: total biomass (W), fruit biomass (Wf), stem biomass (Wm), leaf area index (LAI), and node number (N).  
- Produces a multi-panel line plot to visualise trajectories of all variables across time, with independent scaling for clearer interpretation.  

### **simulation.Rmd**
This R Markdown file is used to explore and identify patterns in tomato growth across different environmental and management conditions. It uses the reduced tomato growth model to identify patterns that guide experimental design.
- Defines a parameter grid over temperature, light, manure levels, and plant type.  
- Runs tomato growth model simulations for each parameter combination using the `tomgro_single()` function.  
- Analyzes the impact of key variables (temperature, light, manure, plant type, and duration) on fruit dry weight.  
- Provides data visualisation (scatter plots, smoothed trends, heatmaps) to illustrate model responses and insights for experiment planning.  

### **design.Rmd**
This R Markdown file documents the full workflow for building, evaluating, and selecting experimental designs for the tomato study. It shows how design principles are applied under real greenhouse constraints and identifies the gold standard design.   
- Demonstrates code to generate experimental designs under realistic constraints (e.g., number of seeds, treatment levels, blocks).
- Computes and compares design optimality criteria (D-, A-, G-optimality) using the generated designs.
- The gold standard design was chosen as the layout that achieved the best overall balance of statistical efficiency (D/A/G-optimality)
- Introduces Completely Randomized Designs (CRD), Randomized Complete Block Designs (RCBD), and custom blocking structures (e.g., light, temperature).  
- Visualises the relative efficiency of each design to guide the choice of optimal setup for tomato experiments.  
- Includes analysis of **thrived** (high-yield) and **survived** (minimum-yield) manure ranges, comparing mean efficiencies of designs that fall fully within these biological thresholds against those that do not. 

### **Suggestion.Rmd**
This R Markdown file documents the process of generating feedback for student experimental designs by comparing them against gold standard benchmarks.  
- Implements functions to compute and compare D-, A-, and G-optimality at both global and parameter-specific levels.  
- Identifies weaknesses such as limited treatment coverage or isolated plots through variance ratio and prediction diagnostics.
- Includes code to safely extract variance-ratio vectors and evaluate whether D- and A-optimality identify the same problematic variables (strict match checking). 
- Translates diagnostic results into **student-friendly suggestions**, linking statistical efficiency losses to concrete greenhouse factors (fertilizer, temperature, light, plant type).  
- Demonstrates the end-to-end feedback pipeline, from input design to optimality computation and final suggestions, with flowcharts and worked examples.  


## Getting Started

1. Clone this repository and open it in RStudio.
2. Install required R packages if needed (e.g., `tidyverse`, `ggplot2`, `dplyr`, `MuMIn`).
3. Knit the R Markdown files to generate HTML reports with interactive plots and results.
