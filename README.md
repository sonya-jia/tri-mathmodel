# Chance in Games: Skill vs. Luck in March Madness

This project analyzes the balance of **skill and chance** in NCAA March Madness games. Using data from three seasons (2021–2024), we created a skill metric for each team and used a **Bayesian logistic regression model** (with the Metropolis-Hastings algorithm) to predict tournament outcomes.  

## Project Goals

1. Identify a rational metric of team skill.
2. Quantify the contribution of skill vs. chance in predicting game outcomes.
3. Predict the winner of the 2024 March Madness tournament using our model.

## Data Sources

- Game-level data from the 2021–2024 seasons ([Sports Reference](https://www.sports-reference.com/cbb/seasons/men/2022-school-stats.html))
- Provided datasets from the 2024 tournament

## Methods

- **Data Preparation:** Combined multiple CSV files into a clean dataset across seasons.
- **Skill Metric:**  
  - Calculated using both **win fraction** and **point differential**.  
  - Adjusted for consistency (variance) over time.  
- **Bayesian Modeling:**  
  - Modeled probability of winning as a function of skill.  
  - Used diffuse priors and the **Metropolis-Hastings algorithm** to sample the posterior distribution.  

## Key Results

- The skill metric based on **point differential** performed better than win fraction alone.  
- Our model ranked **UConn** as having the second-highest probability of winning the 2024 tournament.  
- UConn ultimately won the 2024 March Madness tournament, suggesting that the model captured true skill effectively.

## Files

- `Chance_in_Games.qmd` – Main Quarto analysis document
- `bbdata23-24/` – Folder containing 2023–2024 season team CSVs
- `data22-23/` – Folder containing 2022–2023 season team CSVs
- `data21-22/` – Folder containing 2021–2022 season team CSVs
- `README.md` – This file

## How to Run

1. Clone this repository or download the files.
2. Open the `Chance_in_Games.qmd` file in [RStudio](https://posit.co/download/rstudio/).
3. Ensure the following R packages are installed:  
   ```r
   install.packages(c("dplyr", "knitr", "readr", "ggplot2", "patchwork", "coda"))
