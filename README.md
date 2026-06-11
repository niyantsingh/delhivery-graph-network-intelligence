# 🚚 Delhivery Graph-Based Network Intelligence

## Overview

This project develops a graph-based intelligence system for Delhivery's logistics network to improve ETA prediction accuracy, identify network bottlenecks, and support operational decision-making.

Traditional routing systems treat corridors independently. This solution models the logistics network as a connected graph where facilities act as nodes and shipment corridors act as edges, enabling network-aware ETA prediction and bottleneck detection.

---

## Business Problem

Delhivery's ETA estimation relies heavily on OSRM routing predictions.

Analysis revealed that:

* OSRM systematically underestimates actual delivery times.
* Hub congestion and corridor delays significantly impact ETA accuracy.
* Existing predictions lack network-level operational intelligence.
* High-delay hubs create cascading effects across multiple routes.

The objective was to build a graph-enhanced framework capable of:

* Improving ETA prediction accuracy
* Identifying critical bottleneck facilities
* Detecting chronic delay corridors
* Supporting FTL vs Carting decisions
* Providing actionable operational recommendations

---

## Dataset

| Metric             | Value        |
| ------------------ | ------------ |
| Shipment Records   | 144,867      |
| Trips              | 14,817       |
| Logistics Hubs     | 1,590        |
| Directed Corridors | 2,508        |
| Route Types        | FTL, Carting |

---

## Methodology

### 1. Exploratory Data Analysis

* Delay distribution analysis
* Route type comparison
* Corridor performance analysis
* Hub volume assessment
* Correlation analysis

### 2. Graph Construction

Directed Network:

* Nodes → Logistics Facilities
* Edges → Shipment Corridors

Graph Metrics:

* Betweenness Centrality
* PageRank
* In-Degree
* Out-Degree

---

### 3. Feature Engineering

Operational Features:

* Corridor Delay Statistics
* Hub Delay Profiles
* Corridor Volume Metrics
* Route-Type Features

Graph Features:

* Source Betweenness
* Destination Betweenness
* Source PageRank
* Destination PageRank
* Network Connectivity Metrics

---

### 4. ETA Prediction Models

#### Baseline Model

Traditional ETA prediction using route-level features.

#### Corridor + Hub Enhanced Model

Added operational corridor and hub intelligence.

#### Graph-Based Model

Integrated graph topology metrics into prediction pipeline.

---

## Results

### Model Performance

| Model                | MAE (Minutes) |
| -------------------- | ------------- |
| Baseline Model       | 53.40         |
| Corridor + Hub Model | 38.39         |
| Graph Model          | 38.31         |

### Improvement

* 28% reduction in prediction error compared to baseline.
* Significant operational insights gained from graph analysis.
* Improved identification of network bottlenecks and chronic delay corridors.

---

## Key Insights

### Bottleneck Detection

Graph analysis identified high-impact facilities that contribute disproportionately to network-wide delays.

### Corridor Intelligence

Several corridors consistently exhibited elevated delay factors and were prioritized for intervention.

### FTL vs Carting Framework

Analysis supports route-type selection based on:

* Distance
* Hub congestion
* Corridor delay history
* Operational risk

---

## Repository Structure

```text
ETA/
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── baseline_model.ipynb
│   ├── 04_graph_construction.ipynb
│   ├── 06_bottleneck_analysis.ipynb
│   ├── 07_graph_model.ipynb
│   └── 08_ftl_carting.ipynb
│
├── graphs/
│
├── outputs/
│
├── reports/
│
└── requirements.txt
```

---

## Deliverables

* Graph Construction Pipeline
* Bottleneck Hub Analysis
* Delay Corridor Analysis
* ETA Prediction Models
* FTL vs Carting Decision Framework
* Network Operations Strategy Memo

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* LightGBM
* NetworkX
* Matplotlib
* Jupyter Notebook

---

## Impact

This solution demonstrates how graph intelligence can transform logistics planning by combining operational data with network topology, enabling more accurate ETA prediction and targeted intervention at critical network bottlenecks.
