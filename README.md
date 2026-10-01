# CSCI6840-Homework-2

## Scatter plot

Below is an scatter plot of the provided CSV file. Red dots are anomolgies while blue are normal observations. 


![alt text](image.png)

## Choosing W and q

- **Window Size ($W = 100$):** 
  Records were taken twice every hour (30-minute intervals). Choosing $W = 100$ sets a rolling window of ~50 hours (roughly 2 days). Two days is an optimal size to adapt to localized weather events and short-term runoff shifts without lagging behind long-term seasonal trends.

- **Percentile Threshold ($q = 90$):** 
  Coupled with a 50-hour window size, taking the upper 90th percentile of each window maintains high sensitivity to detect high-concentration runoff spikes.

## Normal accuracy and Anomaly accuracy

- **TP:** 122 | **FN:** 19
- **TN:** 24,830 | **FP:** 5,819
- **Normal Point Accuracy:** 81.01% 
- **Anomaly Point Accuracy:** 86.52% 

## Design Choice

- **Point-Level Evaluation:** 
  To keep comparsion simple, I did a direct array-to-array comparison between my predictions and the ground truth (df["Student_Flag"]) and evalued all predictions with the corresponding student observation. 
