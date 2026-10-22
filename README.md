# NYC Flight Delays and Weather: Join Coverage and EDA

**Author:** Cameron Batts

## Validation update - October 22, 2026

The R workflow now executes and renders. It confirms 336,776 flights, 26,115 weather records, 335,220 matched flights and 1,556 unmatched weather rows. Matched flights contain 8,227 missing departure delays; observed mean delay is 12.635 minutes, median -2, and 13,287 flights exceed 100 minutes. The earlier Python checks agree. Restricted weather plots remain descriptive and cannot establish causes.

[Aggregate validation record](Reports/validation_results.json). [Executed R workflow](Reports/executed_workflow.html) · [Recorded R environment](Reports/validated_session.txt).

Run `Rscript validation/rerun_analysis.R` from the project root.

## Problem
Explore departure-delay distributions and weather associations while documenting unmatched and missing records.

## Approach
Validate unique airport-hour weather keys, retain all flights in a left join, and explicitly reproduce the original weather-matched population. Compare weather plots within the original delay-over-100-minute subset.

## Historical findings and original context
Independent checks using the Python nycflights13 data copy reproduced 336,776 flights and 26,115 weather records. The join matched 335,220 flights and left 1,556 unmatched. Among matched flights, 8,227 had missing departure delays; the observed mean was 12.635 minutes, median −2 minutes and 75th percentile 11 minutes. The severe-delay subset contains 13,287 flights.

## Limitations
The historical inner join omitted flights without matching weather. Missing departure delay is a cancellation proxy, not independently confirmed status here. Weather plots conditioned on delays over 100 minutes cannot identify general delay drivers or establish operational causes. No predictive model or ranked weather importance was estimated.

## Data
Data are supplied by the nycflights13 R package. The independent check used the packaged Python copy for the same 2013 data; the revised R code has now been executed and rendered.

## Verification
Counts and relevant numerical findings were checked independently in Python. The revised R workflow was executed and rendered during this pass. Historical images are retained separately from the revised workflow.

## Run
Install R and Pandoc (or use RStudio), then run from the repository root:
```r
source("install.R")
rmarkdown::render("Notebooks/nyc_flight_delay_analysis.Rmd")
```
R package versions are recorded in Reports/validated_packages.csv and Reports/validated_session.txt. No API key is needed for the default workflow.

## Files
- [R Markdown analysis](Notebooks/nyc_flight_delay_analysis.Rmd)
- [Readable analysis](Reports/nyc_flight_delay_analysis.html)
- [Portfolio report](https://cameron-batts.github.io/nyc_flight_delay_analysis.html)
- [Historical PDF](Reports/NYC%20Flight%20Delay%20%26%20Anomaly%20Detection.pdf): may predate interpretation corrections.

## References
- [nycflights13 data documentation](https://nycflights13.tidyverse.org/)
