# README

## Local Outlier Factor (LOF) Based Anomaly Detection in Synthetic Data Stream

This project demonstrates the implementation of an anomaly detection system using the Local Outlier Factor (LOF) algorithm on a synthetic data stream. The system identifies anomalies by calculating the LOF scores and flagging data points that have LOF scores exceeding a defined threshold.

### Table of Contents

1. [Project Overview](#project-overview)
2. [Dependencies](#dependencies)
3. [Code Structure](#code-structure)
4. [Usage](#usage)
5. [Algorithm Explanation](#algorithm-explanation)
6. [Visualization](#visualization)

---

### Project Overview

The core idea behind this project is to generate a synthetic data stream and use LOF to detect anomalies. The synthetic data simulates a noisy seasonal pattern, occasionally interrupted by anomalous spikes.

### Dependencies

Make sure to have the following Python libraries installed before running the code:

- `numpy`
- `scikit-learn`
- `matplotlib`

You can install the dependencies using the following command:

```bash
pip install numpy scikit-learn matplotlib
```

### Code Structure

1. **`generate_synthetic_data_stream(n_samples)`**: Generates a synthetic time-series data stream with noisy seasonal patterns and occasional anomalous spikes.
2. **`calculate_lrd(data, k)`**: Calculates the Local Reachability Density (LRD) for each point in the data.
3. **`calculate_lof(data, k)`**: Computes the Local Outlier Factor (LOF) for each point based on its neighbors.
4. **Anomaly Detection**: The LOF scores are compared to a threshold to detect and highlight anomalies.
5. **Visualization**: Plots the data stream and highlights the detected anomalies.

### Usage

1. Clone the repository or copy the code.
2. Import the necessary dependencies as mentioned in the `Dependencies` section.
3. Modify parameters like `k` (number of neighbors) and `threshold` (LOF score threshold) to suit your use case.
4. Run the script to generate a synthetic data stream, detect anomalies, and visualize the results.

```bash
python lof_anomaly_detection.py
```

### Algorithm Explanation

The algorithm primarily uses the **Local Outlier Factor (LOF)** method for anomaly detection. LOF is an unsupervised algorithm that assigns each data point a score representing its "outlierness" by comparing the density of its local neighborhood.

#### Steps:

1. **Synthetic Data Generation**:
    - A noisy, seasonal pattern is generated.
    - Occasionally, anomalous values are added to simulate anomalies.
   
2. **Local Reachability Density (LRD)**:
    - For each data point, the k-nearest neighbors are identified.
    - The **reachability distance** between points is computed.
    - Using these distances, the **local reachability density** (LRD) is calculated for each point.

3. **Local Outlier Factor (LOF)**:
    - The LOF score is the ratio of the LRD of a point to the LRD of its neighbors. A score much greater than 1 indicates that the point is an outlier compared to its neighbors.

4. **Anomaly Detection**:
    - Points with LOF scores exceeding a given threshold are flagged as anomalies.

### Visualization

The output of the program includes two plots:
1. **Original Data Stream**: A line plot showing the synthetic data stream.
2. **Data Stream with Detected Anomalies**: The same plot but with detected anomalies highlighted in red.

---

This repository demonstrates a simple yet effective way to detect anomalies in time-series data using the Local Outlier Factor algorithm. Modify the parameters as needed to test the detection on different types of data or thresholds.

