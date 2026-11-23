# cintel-04-rolling-monitoring-custom

[Documentation](https://jrwebb7.github.io/cintel-04-rolling-monitoring-custom/) ·
[GitHub Actions](https://github.com/jrwebb7/cintel-04-rolling-monitoring-custom/actions) ·
[MIT License](LICENSE)

## Project Overview

**Author** James Webb (`jrwebb7`)

**Date** 2026-11

This project will use simulated fellowship onboarding data to see whether a
backlog is building over time. It will compare three-day and five-day rolling
windows to see which picks up a rise in open tasks sooner and which smooths
out day-to-day swings more effectively.

## Planned Data and Measures

Each row will represent one workday and include the number of tasks due, the
number of those tasks completed on time, and the number of tasks still open
at the end of the day. The rolling on-time completion rate will divide the
number completed on time by the number due across the window. A rate will
only be calculated when the window contains at least one task due.

Workflow C sets up the repository and verifies the starter system-metrics
example. The simulated data and window comparison are planned for Workflow D.

## Run the Starter Example

From the project root, install the dependencies, run the Polars pipeline, and
run the smoke test.

```bash
uv python install
uv sync
uv run python -m cintel.rolling_monitor
uv run pytest
```

The starter pipeline reads `data/system_metrics_timeseries.csv` and writes
`artifacts/rolling_metrics.csv`. Run the reactive app to try changing the
rolling window interactively.

```bash
uv run marimo run src/cintel/app.py
```

## Developer Tools

Python 3.14 and uv manage the environment, Polars calculates rolling
statistics, and marimo displays interactive results. Prek runs Git hooks,
Ruff handles linting and formatting, ty checks Python types, and pytest runs
the tests. Zensical and GitHub Actions build and publish the documentation.

## Template Credit

Based on Denise Case's [rolling monitoring template](https://github.com/denisecase/cintel-04-rolling-monitoring).
