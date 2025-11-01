# Customer Segmentation Using Clustering

## Project Overview 
This project focuses on **Customer Segmentation** through unsupervised machine learning to group customers based on **demographic and their purchase history**. The goal is to identify distinct customer profiles from raw, mixed data. 

Three clustering algorithms **(K-Means**, **Hierarchical Clustering**, and **DBSCAN)** are implemented from scratch and evaluated using three internal metrics:  
- **Separation to Spread Ratio**  
- **Calinski–Harabasz (CH) Index**  
- **Davies–Bouldin Index (DBI)**  


## Dataset and Preprocessing

### Dataset Description
- **marketing_campaign.csv** — The *raw dataset* containing customer demographic, purchase, and campaign data.  

### Data Cleaning and Transformation
All preprocessing steps are detailed in **Customer_Data_Cleaning.ipynb**.  
This notebook performs:
1. **Handling Missing Values:** Replaced missing numeric values(observed in the feature'Income') with the median value.
2. **Creating Conclusive Columns:** For repetitve variety features, like 'Total_Spending' and 'Total_Campaigns_Accepted'.
3. **Encoding Categorical Data:** Can be seen for the feature 'Education' and 'Marital_Status'.    
4. **Dimensionality Reduction:** Applied Principal Component Analysis (PCA) to reduce dimensionality while retaining maximum variance.

### Cleaning Outputs
Here are the details of the data files gained after data cleaning:
1. **cdata.csv:** It contains cleaned data with features similar to original features as raw data. It is used further for drawing customer insights per cluster(group).
2. **cleaned_customer_data.csv:** This is the data file produced after PCA was performed, and has reduced dimensions. It is the main data file upon whicih the clustering algorithms were performed. 

---


## Technologies Used (Dependencies and Requirements)
| Category | Tools |
|-----------|--------|
| **Language** | Python |
| **Libraries** | NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, SciPy |
| **Environment** | Google Colab |

---

## Project Files Description
| File Name | Description |
|------------|-------------|
| **marketing_campaign.csv** | Original raw dataset containing customer information. |
| **Customer_Data_Cleaning.ipynb** | Notebook demonstrating all preprocessing, encoding, and PCA steps. |
| **cdata.csv** | Cleaned dataset preserving original feature structure, futher used for drawing customer insights. |
| **cleaned_customer_data.csv** | PCA-transformed dataset used for clustering. |
| **DBSCAN_Clustering.ipynb** | Implements DBSCAN clustering from scratch. |
| **Hierarchical_Clustering.ipynb** | Implements Hierarchical Clustering from scratch. |
| **K_means_code.ipynb** | Implements K-Means Clustering from scratch. |
| **all_outputs.txt** | Contains results(cluster labels) of all three clustering algorithms (in order: DBSCAN → Hierarchical → K-Means). |
| **Clustering_Comparison.ipynb** | Evaluates clustering results using three custom-built metrics. |
| **Project_Report.pdf** | Consolidated project report and findings. |

---

## Instructions for Running the Project

(The data cleaning python notebook(Customer_Data_Cleaning.ipynb) does not have to be necessarily run, as the final cleaned datafiles(cdata.csv and cleaned_customer_data.csv) have already been provided.  

### - Required Input Files
For all clustering notebooks, the following files have to be uploaded in Google Colab's 'Files' section:
* `cdata.csv`
* `cleaned_customer_data.csv`
* `all_outputs.txt` (this file is generated after the first clustering notebook is executed)

### - Step-by-Step Execution

#### (1) Data Preprocessing
**Run → `Customer Data Cleaning.ipynb`**
* **Loads:** `marketing_campaign.csv`
* **Processes:** Cleans, encodes, scales, and applies PCA
* **Generates:** `cdata.csv`, `cleaned_customer_data.csv`

#### (2) Run Clustering Notebooks
There are three clustering notebooks:
1. `DBSCAN_Clustering.ipynb`
2. `Hierarchical_Clustering.ipynb`
3. `K_means_code.ipynb`

**These notebooks can be run in any order, independently**, but in this project they were executed sequentially as:  
**DBSCAN → Hierarchical → K-Means**

**Execution Flow:**

(a) **Run `DBSCAN_Clustering.ipynb`**
   * **Input Files:** `cdata.csv`, `cleaned_customer_data.csv`
   * **Output:** Generates `all_outputs.txt` containing DBSCAN clustering results.

(b) **Run `Hierarchical_Clustering.ipynb`**
   * **Input Files:** `cdata.csv`, `cleaned_customer_data.csv`, and the previously generated `all_outputs.txt`
   * **Output:** Appends hierarchical clustering results to `all_outputs.txt`.

(c) **Run `K_means_code.ipynb`**
   * **Input Files:** `cdata.csv`, `cleaned_customer_data.csv`, and the updated `all_outputs.txt`
   * **Output:** Produces the final version of `all_outputs.txt` containing clustering results for all three algorithms (DBSCAN → Hierarchical → K-Means).

#### (3) Run Evaluation
After completing all clustering notebooks, run:  
**`Clustering_Comparison.ipynb`**

* **Input Files:**
   * `cleaned_customer_data.csv`
   * Final `all_outputs.txt`

This notebook evaluates and compares the clustering methods using:
* Separation / Spread Ratio
* Calinski–Harabasz (CH) Index
* Davies–Bouldin Index (DBI)

---
## Experimental Results


| **Metric** | **K-Means** | **Hierarchical** | **DBSCAN** |
|:---------------------------|:---------:|:--------------:|:--------:|
| **Separation to Spread Ratio** | 1.1649 | **2.4407** | 2.3936 |
| **CH - Index** | 86.743 | **97.278** | 78.566 |
| **DBI** | 3.431 | **0.819** | 1.009 |

---

### Final Inference
*  Dimensionality reduction using **PCA** significantly improved computational efficiency and interpretability.
*  Each clustering notebook performs independently and produces clustering results.
*  The cluster labels are exported into `all_outputs.txt`, enabling comparison across models.
* **Evaluation:** Final metrics (Separation to Spread Ratio, CH Index and DBI) are displayed in `Clustering_Comparison.ipynb`.
* **Hierarchical Clustering** achieved the highest **Separation/Spread ratio (2.44)** and **CH Index (97.27)**, along with the lowest **DBI (0.82)**, indicating compact and well-separated clusters.
*  **DBSCAN** closely followed, effectively handling noise and outliers but slightly less cohesive.
*  **K-Means** showed higher intra-cluster variation, likely due to sensitivity to initialization and spherical cluster assumptions.
  
Overall, **Hierarchical Clustering** was found to be the most robust and effective clustering method for this dataset.

---

## Contributors
**Layaa Vishwakarma (M25CSA017)**
**Prapti Halder (M25CSA022)**  
**Suparni Maitra (M25CSA029)**  

*Course: CSL7620 – Machine Learning (Semester I)*  
*November 2025*  
*Indian Institute of Technology Jodhpur*

---
