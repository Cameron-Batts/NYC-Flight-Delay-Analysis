# NYC Flight Delay & Anomaly Detection

**Tools:** R · tidyverse · ggplot2 · cowplot · nycflights13 · dplyr

---

## Problem

Airlines and airports needed to understand which weather conditions were most strongly associated with flight delays and cancellations across New York City airports, and to identify delays that could not be explained by weather for further investigation.

## Approach

Analyzed 336,776 flights from the nycflights13 dataset in R, merging flight and weather data on origin airport and time. Applied the Fraud Analytics Process Model to clean, transform, and analyze the data. Visualized relationships between departure delays and nine weather variables including temperature, visibility, wind speed, precipitation, and pressure using scatter plots and histograms.

## Impact

Found no strong correlation between departure delays over 100 minutes and any weather variable, suggesting operational issues as the more likely cause. This subset of flights provides a focused starting point for further investigation into non-weather-related delay causes.

---

## Files

| File | Description |
|------|-------------|
| `nyc_flight_delay_analysis.Rmd` | R Markdown source file with full analysis |
| `nyc_flight_delay_analysis.html` | Rendered HTML output |

---

*Part of my data & analytics portfolio — [cameronbatts.github.io](https://cameronbatts.github.io)*
