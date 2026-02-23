# Quantitative Analysis of Actin Filament Orientation Using OrientationJ

## Overview

This repository contains Python scripts used to quantify and visualize actin filament orientation distributions in *C. elegans* embryos.

Orientation data were extracted using the Fiji plugin- OrientationJ (‘OrientationJ (OJ) Distribution (Rezakhaniha et al., 2012)’) and exported as CSV files. The provided Python script processes these CSV files to compute normalized angular distributions and generate polar plots representing mean filament orientation across embryos.

This analysis was performed for control and RNAi-treated embryos by substituting the appropriate CSV input files.

---

## Experimental Context

- Organism: *C. elegans*
- Analysis region: Medial cortex during actomyosin ring assembly.
- Image analysis tool: OrientationJ (Fiji/ImageJ plugin)
- Output: Polar probability distribution of filament orientations (0°–90°)

---

## Input Data

The script expects CSV files generated from OrientationJ Distribution.

Each CSV file:

- Represents a single embryo orientation distribution histogram data
- Contains orientation distribution data across angles (-89.5° to 89.5°)
- Columns correspond to video frames
- Rows correspond to angular bins

## Software Requirements

- Python 3.9+
- numpy
- matplotlib
- Jupyter Notebook (optional)
- Fiji/ImageJ with OrientationJ plugin

## How to Run

1. Place CSV files in the same directory as the script.
2. Open the Jupyter notebook.
3. k values(k1,k2,...k11) represent the frame number during furrow ingression for different embryos(change according to embryos)
3. Run all cells sequentially.
4. Figure will be generated automatically.

## Output

The script generates:

- Normalized angular distribution plot(for single embryo)
- Mean orientation polar plots(for all embryos)
