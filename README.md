# Clinker Cooler Spare-Part Classification

Explainable semi-supervised clustering framework for 51 clinker cooler spare parts at PT Semen Gresik (Persero) Tbk.

## Overview

Classification of spare parts under intermittent demand using constrained K-means clustering with 6 demand-behaviour criteria. The framework produces stable priority classes (A/B/C) with explicit review workloads and fidelity-gated explainability.

**Data:** 598 issue transactions from SAP Material Item Ledger, January 2021 - May 2025.

## Files

| File | Description |
|---|---|
| `index.html` | Interactive dashboard (self-contained, open in browser) |
| `Klasifikasi_Sparepart_Prozima.ipynb` | Analysis notebook (Python) |
| `Figure_1_cluster_projection.png` | PCA projection of classified items |
| `Figure_2_assignment_stability.png` | Bootstrap assignment probability heatmap |
| `Figure_3_global_shapley.png` | Global Shapley feature importance |

## Classes

| Class | N | Role | Review |
|---|---|---|---|
| A | 10 | Economically exposed, high priority | Monthly |
| B | 15 | Active, recent, variable, least stable | Monthly + quarterly |
| C | 26 | Sparse, low activity | Semi-annual |

## Criteria

- **EV** - Economic Exposure (log cumulative adjusted issue value)
- **DM** - Demand Magnitude (log mean positive monthly quantity)
- **TF** - Transaction Frequency (transactions per month)
- **ZR** - Zero-demand Ratio (proportion of zero-demand months)
- **DS** - Demand-size Instability (log(1 + CV^2))
- **RS** - Recency Score (exponential decay since last issue)

## Requirements

- Python 3.10+
- pandas, NumPy, SciPy, scikit-learn, matplotlib, seaborn, openpyxl

## Citation

If using this code or methodology, please cite the original research article.
