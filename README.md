
# What Makes a Good MLB Hitter?

### An R-Based Statistical Analysis of the 2025 MLB Season

**Status:** Completed | October 2026

## Project Overview

This project investigates the relationship between traditional and advanced batting statistics and overall offensive performance in Major League Baseball.

Using data from the 2025 MLB season, the analysis examines how batting average (AVG), on-base percentage (OBP), slugging percentage (SLG), and isolated power (ISO) relate to Weighted Runs Created Plus (wRC+).

The project uses exploratory data analysis, visualization, correlation analysis, linear regression, and model diagnostics to evaluate the strengths and limitations of different offensive statistics.

## Research Questions

- How strongly does batting average correlate with wRC+?
- Is on-base percentage more strongly associated with offensive production than batting average?
- What role does hitting power play in offensive performance?
- Can combining offensive statistics improve regression model fit?
- How reliable are these relationships when evaluated using regression diagnostics?

## Data and Methodology

Data was retrieved from FanGraphs using the `baseballr` R package.

The dataset includes 348 MLB hitters from the 2025 regular season who met a minimum threshold of 200 plate appearances.

The following statistical methods were used:

- Exploratory data analysis and descriptive statistics
- Pearson correlation analysis
- Data visualization using ggplot2
- Simple and multiple linear regression
- Model comparison using R-squared, adjusted R-squared, and residual standard error
- Multicollinearity assessment using Variance Inflation Factor (VIF)
- Residual diagnostics and Cook's distance
- Sensitivity analysis of influential observations

## Results

### 1. Individual Offensive Statistics

All four offensive statistics demonstrated positive correlations with wRC+.

| Statistic | Pearson's r | R-squared |
|---|---:|---:|
| Batting Average (AVG) | 0.731 | 0.5350 |
| On-Base Percentage (OBP) | 0.878 | 0.7705 |
| Slugging Percentage (SLG) | 0.910 | 0.8273 |
| Isolated Power (ISO) | 0.739 | 0.5456 |

Among individual statistics, SLG demonstrated the strongest relationship with wRC+, followed by OBP.

These findings suggest that statistics incorporating additional offensive contributions beyond batting average provide a more complete description of overall hitting performance.

### 2. Multiple Linear Regression

A multiple linear regression model was developed using OBP and ISO as predictors of wRC+.

The resulting equation was:

**Predicted wRC+ = -94.898 + 507.000(OBP) + 220.774(ISO)**

The combined model achieved:

| Model Statistic | Result |
|---|---:|
| R-squared | 0.9628 |
| Adjusted R-squared | 0.9626 |
| Residual Standard Error | 4.923 |

The combined model accounted for approximately 96.3% of the observed variation in wRC+, substantially outperforming the individual models in terms of in-sample fit.

### 3. Multicollinearity

Multicollinearity was assessed using Pearson correlation and Variance Inflation Factor (VIF).

| Statistic | Result |
|---|---:|
| Correlation between OBP and ISO | 0.379 |
| VIF for OBP | 1.168 |
| VIF for ISO | 1.168 |

These results suggest that multicollinearity was not a major concern in the combined model.

### 4. Residual Diagnostics

Residual diagnostics were conducted to evaluate the assumptions of the multiple regression model.

The analysis identified:

- A slight curved pattern in the residuals versus fitted values plot
- Minor deviations from normality at the extremes of the Q-Q plot
- Possible changes in residual variance across fitted values
- Several potentially influential observations

These findings suggest that although the model fits the observed data well, some regression assumptions may not be fully satisfied.

### 5. Influential Observations and Sensitivity Analysis

Cook's distance was used to identify potentially influential observations.

Aaron Judge had the highest Cook's distance at approximately 0.144.

A sensitivity analysis was conducted by fitting the model with and without Judge.

| Statistic | Full Model | Without Judge |
|---|---:|---:|
| OBP Coefficient | 507.000 | 510.246 |
| ISO Coefficient | 220.774 | 222.425 |
| R-squared | 0.9628 | 0.9617 |

The relatively small changes suggest that the overall findings were not heavily dependent on Judge's observation.

## Key Findings

The analysis suggests that evaluating offensive performance requires considering multiple aspects of hitting rather than relying on batting average alone.

Batting average remains useful because recording hits can extend innings, advance runners, and create scoring opportunities. However, it does not capture walks or distinguish between singles and extra-base hits.

OBP provides additional information about a player's ability to reach base, while ISO measures extra-base hitting power.

Combining OBP and ISO produced the strongest overall model fit, highlighting the value of examining both on-base ability and power when evaluating offensive performance.

## Limitations

This analysis examines relationships between offensive statistics from the same MLB season.

Because the predictors share underlying components with wRC+, strong correlations and regression fit are partly expected.

Additionally, residual diagnostics identified possible departures from certain regression assumptions.

The models should therefore be interpreted as descriptive rather than causal or predictive. They do not establish how accurately these statistics can forecast future player performance.

## Tools and Technologies

- R and RStudio
- R Markdown
- baseballr
- tidyverse
- ggplot2
- Pearson correlation
- Simple and multiple linear regression
- Regression diagnostics

## Future Research

A potential extension would involve using historical MLB data to predict offensive performance in subsequent seasons.

Future analyses could investigate:

- Identifying potential breakout hitters
- Evaluating year-to-year consistency in offensive performance
- Comparing traditional and advanced statistics for forecasting
- Building predictive models with training and testing datasets

## Project Status

**Completed - October 2026**

This project was developed as a personal learning and portfolio exercise to strengthen practical skills in R programming, statistical modelling, and baseball analytics.

AI assistance was used for coding guidance, debugging, and writing feedback.

## Data Source

FanGraphs - 2025 MLB batting statistics, accessed through the `baseballr` R package.
