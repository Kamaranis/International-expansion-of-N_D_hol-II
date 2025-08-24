# Strategic Market Analysis for International Expansion (Part II)
## 📄 Project Overview

This repository represents **Part II** of a comprehensive strategic analysis to guide the international expansion of the fictional company "N&D.hol". Building upon the meticulously prepared dataset from **[Part I: Data Preparation]([Strategic Market Clustering for International Expansion (Part I)](https://github.com/Kamaranis/Strategic-Market-Analysis-for-International-Expansion-Part-I-))**, this phase applies unsupervised machine learning techniques to segment and identify promising markets.

The primary goal is to move from a clean dataset to actionable business insights by grouping countries based on their socio-economic, demographic, and business environment characteristics. The project culminates in a final, data-driven list of candidate countries for expansion.

## ✨ Analysis Showcase & Methodology

This project provides a comparative analysis of various clustering algorithms, demonstrating a robust approach to identifying underlying patterns in complex, high-dimensional data.

*   **Dimensionality Reduction with PCA:**
    *   **Principal Component Analysis (PCA)** was first applied to the standardized dataset to understand the key drivers of variance among countries.
    *   The first two principal components captured over **55%** of the data's variability, revealing significant contributions from variables like healthcare personnel density (`phy_z`), business confidence (`bci_z`), and government investment (`imf_z`). This step was crucial for visualizing clusters in a 2D space.

*   **Centroid-Based Clustering (K-Means):**
    *   The **K-Means algorithm (k=3)** was used to partition countries into three distinct socio-economic groups.
    *   Clusters were analyzed to identify target groups matching the business requirements, such as countries with high GDP growth and a significant elderly population.

*   **Density-Based Clustering (DBSCAN & OPTICS):**
    *   **OPTICS** was used to explore the data's density structure, generating reachability plots to identify potential clusters and noise.
    *   **DBSCAN** was then applied to formally segment countries into clusters and identify outliers. This method proved effective in separating high-density groups (e.g., highly developed nations) from the rest.

*   **Robust Clustering with PAM:**
    *   The **Partitioning Around Medoids (PAM)** algorithm was implemented with both **Manhattan** and **Minkowski** distance metrics as a robust alternative to K-Means, less sensitive to outliers.
    *   The results from PAM provided a more refined grouping, identifying a key cluster of developing countries with positive growth indicators.

## 🏆 Results & Final Candidate Selection

The analysis concluded with a comparison of all clustering methods. While density-based models effectively isolated very wealthy nations, the partitioning-based algorithms (**K-Means and PAM**) provided a more balanced and actionable segmentation.

Based on the clusters identified, a final filtering process was applied to select candidate countries that met the specific business criteria:
*   **GDP Growth (`gdp_z`) > 1.5**
*   **High population in the 50-70 age bracket**

This resulted in a curated list of high-potential markets for investment, primarily concentrated in **Africa, Oceania, and developing regions of Asia.**

| Cluster Algorithm | Key Finding |
| :--- | :--- |
| **K-Means** | Produced three well-balanced socio-economic clusters. |
| **PAM (Minkowski)**| Refined the clusters, isolating a group of promising developing nations. |
| **OPTICS/DBSCAN**| Successfully identified high-density groups, separating top-tier economies. |

## 💻 Technologies Used

*   **Language:** R
*   **Core Libraries:**
    *   **Tidyverse** (`dplyr`, `ggplot2`) for data manipulation and visualization.
    *   **`cluster`** and **`fpc`** for implementing K-Means, PAM, and clustering statistics.
    *   **`dbscan`** for OPTICS and DBSCAN algorithms.
    *   **`ggbiplot`** for PCA visualization.
*   **Environment:** RStudio

## 🚀 Getting Started

To reproduce this analysis:
1.  **Prerequisite:** This project requires the `pra1.csv` dataset, which is the final output of **[Part I of this analysis](https://github.com/Kamaranis/Strategic-Market-Analysis-for-International-Expansion-Part-I-)**.
2.  Clone this repository.
3.  Install the required R packages listed above.
4.  Open the `.Rmd` script in RStudio and execute the cells to follow the modeling, clustering, and final candidate selection process.

## 👤 Author

**Antonio Barrera Mora**

*   **LinkedIn:** https://www.linkedin.com/in/anbamo/
*   **GitHub:** @Kamaranis
