Edge Velocity Analysis During Cytokinetic Furrow Ingression
Overview:

This analysis quantifies instantaneous edge velocities along x and y direction during cytokinetic furrow ingression in C. elegans embryos. It compares Vx (Instantaneous velocity along x- direction) and Vy (Instantaneous velocity along x- direction) of control and cyk-1 RNAi embryos.
Two experimental conditions are compared:
1. Control (l4440 RNAi)
2. cyk-1 RNAi


Velocities are aligned to furrow initiation time(time0), pooled across embryos, and statistically compared between control and cyk-1 RNAi conditions.

Input Data Required:

For each embryo, the following TrackMate-generated files are required:
Edge statistics CSV file
Spot statistics CSV file

Additionally, the following information must be provided:
Frame interval (in seconds, here 5 second is used as Frame interval)
Furrow initiation frame (time zero)
Frame for analysis (Here, 47s to 122s time window is used for plotting histogram)

Each embryo is processed individually before pooling data across embryos.

What the Code Does:

Step 1: Time Alignment
All edge times are aligned to furrow initiation (time zero).
This ensures that all embryos are synchronized to the same biological event.
Step 2: Instantaneous Velocity Calculation
For each edge:
The source and target spot coordinates are identified.
Displacement in X and Y directions is calculated.
Instantaneous velocities are computed as:
Vx (velocity in X-direction)
Vy (velocity in Y-direction)
Velocities are expressed in micrometers per second.
Step 3: Pooling Across Embryos
For each condition (Control and cyk-1 RNAi):
All embryos are combined.
Velocities are grouped by aligned time.
Mean and standard deviation are calculated at each time point.
This generates time-resolved velocity curves for both Vx and Vy.

Comparison Between Control and cyk-1 RNAi
The following are compared between the two conditions:
Mean Vx over time
Mean Vy over time
Distribution of Vx values
Distribution of Vy values
Non-parametric statistical tests are used to determine significance.


Histogram Analysis
For both Vx and Vy:
Velocities from 47–122 seconds(after furrow initiation) are pooled across embryos.This time window corresponds to the active phase of furrow ingression.
Normalized histograms are generated.
Raw velocity values are exported for statistical testing.
This allows comparison of velocity distributions between Control and cyk-1 RNAi.

Output Generated
The script produces:
Time-resolved velocity plots (Vx and Vy)
Histogram plots (47–122 s time window)
CSV files compatible with GraphPad Prism
Raw pooled velocity values for statistical analysis

How to Run the Analysis:
Place all required CSV files(spot and edge files generated from TrackMate) in the working directory.
Update file names in the script for each embryo.
Enter frame interval and furrow initiation frame when prompted.
