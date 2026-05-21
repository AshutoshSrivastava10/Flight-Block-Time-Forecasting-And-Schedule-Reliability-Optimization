# Flight-Block-Time-Forecasting-And-Schedule-Reliability-Optimization
Block time forecasting and schedule buffer optimization using BTS airline on-time performance data, machine learning, and Gurobi.

## Overview

This project analyzes American Airlines flight block times using BTS On-Time Performance data for Virginia/DC-area flights from October to December 2025.

The goal is to compare scheduled flight times with actual elapsed times, identify routes with reliability issues, forecast actual block time, and recommend better schedule buffers using optimization.

## Business Problem

Airlines need to balance reliability and efficiency.

- If scheduled block time is too short, flights are more likely to arrive late.
- If scheduled block time is too long, the schedule becomes inefficient.
- The goal is to add buffer only where it is needed.

## Project Phases

### Phase 1: Data Cleaning and EDA

In this phase, I cleaned the BTS flight data and analyzed route-level block time performance.

Main steps:

- Removed cancelled and diverted flights
- Created route and time-based features
- Compared scheduled elapsed time with actual elapsed time
- Identified underblocked routes and late-arrival patterns
- Created initial schedule buffer recommendations

### Phase 2: Block Time Forecasting

In this phase, I built machine learning models to predict actual elapsed flight time.

Models used:

- Baseline scheduled elapsed time
- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor

The best model predictions were used to estimate where extra schedule buffer may be needed.

### Phase 3: Schedule Buffer Optimization

In this phase, I used Gurobi to recommend route-level buffer adjustments.

The optimization model helps decide:

- Which routes need additional buffer
- How many minutes should be added
- How to improve reliability without adding unnecessary scheduled time

## Tools Used

- Python
- pandas
- NumPy
- scikit-learn
- matplotlib
- seaborn
- Gurobi
- Jupyter Notebook
- BTS On-Time Performance Data

## Repository Structure

```text
flight-block-time-forecasting/
│
├── notebooks/
│   ├── 01_data_cleaning_eda.ipynb
│   ├── 02_block_time_forecasting_model.ipynb
│   └── 03_schedule_buffer_optimization.ipynb
│
├── data/
│   └── processed/
│
├── reports/
│   └── phase_1_eda_report.pdf
│
├── outputs/
│
├── README.md
├── requirements.txt
└── .gitignore
