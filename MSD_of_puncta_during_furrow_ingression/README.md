# Mean Squared Displacement (MSD) Analysis of Tracked Puncta

## Overview

This repository contains Python script used to compute mean squared displacement (MSD) of tracked puncta during furrow ingression. Tracking data were generated using the TrackMate plugin (Fiji/ImageJ) and exported as spot statistics CSV files.

The script calculates MSD within a defined time window and combines results across multiple embryos.

---

## Input Data

The script requires CSV files exported from TrackMate containing the following columns:

- Track ID
- Frame
- X
- Y

Each CSV file corresponds to a single embryo.

- Frame interval must be specified at runtime.
- Time zero (furrow initiation frame) is entered manually.
- Frame window selection determines the analyzed ingression period.

## Analysis Workflow

### 1. Frame Selection

- The user provides the frame interval (`t_gap`) in seconds.
- The user inputs the time zero (furrow initiation frame).
- The start frame is defined relative to time zero (~40 seconds after furrow initiation).
- The end frame(end of cytokinesis seen as end of furrow ingression on cortex) is defined by the user.

Tracks are filtered within this selected frame window before MSD calculation.

---

### 2. MSD Calculation (Per Embryo)

For each embryo:

- Data are grouped by Track ID.
- All possible squared displacements are calculated for each lag within a track.
- Squared displacements are averaged across all tracks for each lag.
- Lag frames are converted to time using the frame interval.

The function `compute_msd_true_average()` performs this calculation.

---

### 3. Multi-Embryo Analysis

MSD is computed independently for 15 embryos.

- Individual MSD DataFrames are concatenated.
- Lag times are automatically aligned.
- Missing lag values appear as NaN.
- The combined dataset is exported as a CSV file.

---

### 4. Log Transformation

For scaling analysis:

- Natural logarithm is applied to each embryo’s MSD dataset.
- Log-transformed DataFrames are concatenated.
- Columns are renamed to:
  - Ln(MSD)
  - Ln(lag time)

This enables log–log visualization and diffusion regime analysis.

---

## Output

The script generates:

- Combined MSD dataset across embryos
- Log-transformed MSD dataset
- Exported CSV files for downstream analysis

---

## Requirements

Python 3.8+

Required packages:

- numpy
- pandas
- matplotlib

---

