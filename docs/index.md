# Rolling Monitoring of Fellowship Onboarding

## Project Plan

This project will compare three-day and five-day rolling windows using
simulated daily onboarding data. The goal is to see how quickly each window
reveals a growing backlog or a decline in on-time task completion.

The results below come from the starter system-metrics dataset. They show
how the pipeline works before it is applied to the onboarding data.

## Overview

This project investigates how rolling statistics
can reveal patterns in system behavior over time.

Individual measurements may fluctuate.
Rolling analysis provides a way to examine
recent behavior while reducing short-term variation.

## Data

The example dataset contains 60 time-ordered observations
collected at five-minute intervals.

Each observation includes:

- Timestamp.
- Number of requests.
- Number of errors.
- Total latency in milliseconds.

[View Example Dataset](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom/blob/main/data/system_metrics_timeseries.csv)

## Methods

The pipeline sorts observations by timestamp
and computes rolling averages using a window
of three observations.

Rolling averages are calculated for:

- Requests.
- Errors.
- Total latency.

Each completed window summarizes the current
observation and the two preceding observations.

The first two rows have no rolling average
because the full window is not yet available.

## Results

The rolling metrics show several changes in activity.

| Time  | Rolling Requests | Rolling Errors |
| ----- | ---------------: | -------------: |
| 08:10 |           135.00 |           3.00 |
| 08:25 |           171.67 |           6.00 |
| 08:50 |           145.00 |           2.33 |
| 09:10 |           198.33 |           7.67 |

[View Rolling Monitoring Results](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom/blob/main/artifacts/rolling_metrics.csv)

## Interpretation

The rolling averages reveal periods of increasing
activity, declining activity, and renewed growth.

From 08:50 to 09:10, both the rolling request count
and the rolling error count increase.

This suggests that growing workload may coincide
with additional errors, although the data
does not establish a causal relationship.

## Limitations

Rolling averages smooth short-term variation,
but may delay detection of sudden changes.

The example uses a fixed three-observation window.
Different window sizes may reveal different patterns.

The pipeline does not yet classify anomalies
or issue monitoring alerts.

## Conclusion

Rolling monitoring adds a temporal perspective
to system analysis.

It provides a foundation for identifying developing
patterns and determining when further investigation
may be useful.

## Documentation Index

- **Home** - this landing page
- [**Project Instructions**](project-instructions.md)
- [**Glossary**](glossary.md)
- [**API**](api.md)
- [**Run the Reactive App**](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom/blob/main/README.md#run-the-starter-example)

## Project Links

- [GitHub Repository](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom)
- [Example Pipeline](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom/blob/main/src/cintel/rolling_monitor.py)
- [Results and Artifacts](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom/tree/main/artifacts)

## Project Resources

- [Project Instructions](project-instructions.md)
- [Professional Python Guide](https://denisecase.github.io/pro-analytics-02/)
- [Professional Python Project Explainer](https://pup-pack.github.io/professional-python-project-explainer/).
- [Suggested Datasets](https://denisecase.github.io/pro-analytics-02/reference/datasets/cintel/)
