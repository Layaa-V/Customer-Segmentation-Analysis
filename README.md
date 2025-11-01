# 🧠 Customer Segmentation Using Clustering

## 📘 Project Overview 
This project focuses on **Customer Segmentation** through **unsupervised machine learning** to group customers based on **demographic and purchase behavior**. The goal is to identify distinct customer profiles for **targeted marketing**, **personalized services**, and **strategic decision-making**.  

Three clustering algorithms — **K-Means**, **Hierarchical Clustering**, and **DBSCAN** — are implemented **from scratch** and evaluated using three internal metrics:  
- **Separation / Spread Ratio**  
- **Calinski–Harabasz (CH) Index**  
- **Davies–Bouldin Index (DBI)**  


## ⚙️ Dataset and Preprocessing

### 📂 Dataset Description
- **marketing_campaign.csv** — The **raw dataset** containing customer demographic, purchase, and campaign data.  

### 🧹 Data Cleaning and Transformation
All preprocessing steps are detailed in **`Customer Data Cleaning.ipynb`**.  
This notebook performs:
1. **Handling Missing Values:**  
   - Replaced missing numeric values with the median and categorical values with the mode.  
2. **Encoding Categorical Data:**  
   - Converted all categorical variables into numerical representations.  
3. **Feature Scaling and Standardization:**  
   - Standardized numerical features to ensure uniform contribution.  
4. **Dimensionality Reduction:**  
   - Applied **Principal Component Analysis (PCA)** to reduce dimensionality while retaining maximum variance.

### 🧾 Cleaning Outputs
Here are a few details about the cleaning part:
1. `marketing_campaign.csv` - raw data  
2. `Customer Data Cleaning.ipynb` - shows steps involved in cleaning; produces two types of data files:  
   - `cdata.csv` (cleaned data with similar original features as raw data)  
   - `cleaned_customer_data.csv` (data file produced after PCA; reduced dimensions; used for clustering)

---


## 💻 Technologies Used (Dependencies and Requirements)
| Category | Tools |
|-----------|--------|
| **Language** | Python |
| **Libraries** | NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, SciPy |
| **Environment** | Google Colab |

---

## ⚙️ Project Files Description
| File Name | Description |
|------------|-------------|
| **marketing_campaign.csv** | Original raw dataset containing customer information. |
| **Customer Data Cleaning.ipynb** | Notebook demonstrating all preprocessing, encoding, and PCA steps. |
| **cdata.csv** | Cleaned dataset preserving original feature structure. |
| **cleaned_customer_data.csv** | PCA-transformed dataset used for clustering. |
| **DBSCAN_Clustering.ipynb** | Implements DBSCAN clustering from scratch. |
| **Hierarchical_Clustering.ipynb** | Implements Hierarchical Clustering from scratch. |
| **K_means_code.ipynb** | Implements K-Means Clustering from scratch. |
| **all_outputs.txt** | Contains results of all three clustering algorithms (in order: DBSCAN → Hierarchical → K-Means). |
| **Clustering_Comparison.ipynb** | Evaluates clustering results using three internal metrics (custom-built). |
| **Final_Report.pdf** | Consolidated project report and findings. |

---

## 🚀 Instructions for Running the Project

### 🧩 Required Input Files
For all clustering notebooks, the following files serve as inputs:
* `cdata.csv`
* `cleaned_customer_data.csv`
* `all_outputs.txt` (this file is generated after the first clustering notebook is executed)

### 🧮 Step-by-Step Execution

#### 1️⃣ Data Preprocessing
**Run → `Customer Data Cleaning.ipynb`**
* **Loads:** `marketing_campaign.csv`
* **Processes:** Cleans, encodes, scales, and applies PCA
* **Generates:** `cdata.csv`, `cleaned_customer_data.csv`

#### 2️⃣ Run Clustering Notebooks
There are three clustering notebooks:
1. `DBSCAN_Clustering.ipynb`
2. `Hierarchical_Clustering.ipynb`
3. `K_means_code.ipynb`

These notebooks can be run in any order, but in this project they were executed sequentially as:  
**DBSCAN → Hierarchical → K-Means**

**Execution Flow:**

1. **Run `DBSCAN_Clustering.ipynb`**
   * **Input Files:** `cdata.csv`, `cleaned_customer_data.csv`
   * **Output:** Generates `all_outputs.txt` containing DBSCAN clustering results.

2. **Run `Hierarchical_Clustering.ipynb`**
   * **Input Files:** `cdata.csv`, `cleaned_customer_data.csv`, and the previously generated `all_outputs.txt`
   * **Output:** Appends hierarchical clustering results to `all_outputs.txt`.

3. **Run `K_means_code.ipynb`**
   * **Input Files:** `cdata.csv`, `cleaned_customer_data.csv`, and the updated `all_outputs.txt`
   * **Output:** Produces the final version of `all_outputs.txt` containing clustering results for all three algorithms (DBSCAN → Hierarchical → K-Means).

#### 3️⃣ Run Evaluation
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
## 📊 Experimental Results


| **Metric** | **K-Means** | **Hierarchical** | **DBSCAN** |
|:---------------------------|:---------:|:--------------:|:--------:|
| **Separation to Spread Ratio** | 1.1649 | **2.4407** | 2.3936 |
| **CH - Index** | 86.743 | **97.278** | 78.566 |
| **DBI** | 3.431 | **0.819** | 1.009 |

---

### 🧾 Final Inference
*  Dimensionality reduction using **PCA** significantly improved computational efficiency and interpretability.
*  Each clustering notebook independently trains a model on the preprocessed data.
*  The trained cluster labels are exported into `all_outputs.txt`, enabling comparison across models.
* **Evaluation:** Final metrics (CH Index, DBI, and Spread Ratio) are displayed in `Clustering_Comparison.ipynb`.
* **Hierarchical Clustering** achieved the highest **Separation/Spread ratio (2.44)** and **CH Index (97.27)**, along with the lowest **DBI (0.82)**, indicating compact and well-separated clusters.
*  **DBSCAN** closely followed, effectively handling noise and outliers but slightly less cohesive.
*  **K-Means** showed higher intra-cluster variation, likely due to sensitivity to initialization and spherical cluster assumptions.
  
Overall, **Hierarchical Clustering** was found to be the most robust and effective clustering method for this dataset.

---

## 👩‍💻 Authors
**Prapti Halder (M25CSA022)**  
**Layaa Vishwakarma (M25CSA017)**  
**Suparni Maitra (M25CSA029)**  

📍 *Course: CSL7620 – Machine Learning (Semester I)*  
📅 *November 2025*  
🏫 *Indian Institute of Technology Jodhpur*

---
