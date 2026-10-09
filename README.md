
# What Makes a Good MLB Hitter?

### An R-Based Analysis of the 2025 MLB Season

**Status:** Work in Progress

## Project Overview

This project investigates the relationship between traditional and advanced batting statistics and overall offensive performance in Major League Baseball.

Using data from the 2025 MLB season, the analysis examines which hitting statistics are most strongly associated with Weighted Runs Created Plus (wRC+).

## Research Questions

- How strongly does batting average correlate with wRC+?
- Is on-base percentage a better indicator of offensive production than batting average?
- How important is hitting power in explaining offensive performance?
- Can multiple regression provide a more comprehensive understanding of hitting performance?

## Preliminary Findings

- Batting average has a strong positive correlation with wRC+ (r = 0.731).
- On-base percentage shows a stronger correlation (r = 0.878).
- Simple linear regression using OBP accounts for approximately 77.1% of the observed variation in wRC+, compared with 53.5% for batting average.

These results describe same-season relationships and do not establish predictive accuracy for future seasons.

## Tools and Technologies

- R
- RStudio
- tidyverse
- ggplot2
- baseballr
- Linear Regression and Correlation Analysis

## Next Steps

- Investigate slugging percentage and isolated power.
- Compare simple and multiple regression models.
- Evaluate model assumptions and limitations.
- Produce a final analytical report.
