# 🧠 Customer Segmentation Using Clustering

## 📘 Project Overview
This project performs **Customer Segmentation** using **unsupervised machine learning** algorithms to group customers based on their **purchase history** and **demographic data**.  
The aim is to uncover distinct, meaningful customer segments to enable **targeted marketing**, **personalized services**, and **strategic decision-making**.

To ensure robustness, the project implements three clustering algorithms — **K-Means**, **Hierarchical Clustering**, and **DBSCAN** — and evaluates them using **three custom-built internal metrics**:  
- Separation / Spread Ratio  
- Calinski–Harabasz (CH) Index  
- Davies–Bouldin Index (DBI)

---

## 🎯 Objectives
- Implement multiple clustering algorithms from scratch for customer segmentation.  
- Perform data preprocessing including missing value handling, categorical encoding, and dimensionality reduction.  
- Evaluate the performance of each clustering technique using custom-built and standard metrics.  
- Identify the most effective clustering method for meaningful customer segmentation.

---

## 🧰 Main Python Libraries Used
| Library | Purpose |
|----------|----------|
| **Pandas** | Data manipulation and preprocessing (loading, grouping, selecting columns). |
| **NumPy** | Numerical operations, array manipulations, and distance calculations. |
| **Matplotlib & Seaborn** | Visualization of clustering results and PCA projections. |
| **Scikit-learn** | Feature scaling, evaluation metrics, and PCA. |
| **SciPy** | Hierarchical clustering implementation and dendrogram visualization. |

---

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

## ⚙️ Workflow of the Project
### 1. **Data Preprocessing**
- Input: `marketing_campaign.csv`  
- Executed via: `Customer Data Cleaning.ipynb`  
- Output: `cdata.csv`, `cleaned_customer_data.csv`  

### 2. **Data Clustering**
Three clustering algorithms were implemented **from scratch** and executed individually on the cleaned (PCA-reduced) dataset.

| Algorithm | File Name | Description |
|------------|------------|-------------|
| **K-Means Clustering** | `K_means_code.ipynb` | Iterative partitioning into *k* clusters using K-Means++ initialization. Optimal *k* determined via hybrid Elbow–Silhouette method. |
| **Hierarchical Clustering** | `Hierarchical_Clustering.ipynb` | Built using Ward's linkage and visualized with a dendrogram. Optimal *k* obtained using silhouette analysis. |
| **DBSCAN** | `DBSCAN_Clustering.ipynb` | Implemented manually with custom Epsilon (eps) and MinPts selection using k-distance graph and grid search. |

Each algorithm appends its clustering results sequentially into a single file:  
**`all_outputs.txt`**  
The results are stored in the following order:
1. DBSCAN  
2. Hierarchical  
3. K-Means  

### 3. **Evaluation of Techniques**
All three clustering results are evaluated in **`Clustering_Comparison.ipynb`**, which includes **custom implementations** of the following metrics:
- **Separation / Spread Ratio:** Measures ratio of cluster separation to intra-cluster spread.  
- **Calinski–Harabasz (CH) Index:** Higher score = better-separated and more compact clusters.  
- **Davies–Bouldin Index (DBI):** Lower score = better clustering.

---

## 📊 Experimental Results

### 🧩 Separation to Spread Ratio
| Method | Ratio |
|---------|------:|
| **Hierarchical** | **2.4407** |
| DBSCAN | 2.3936 |
| K-Means | 1.1649 |

### 🧩 Calinski–Harabasz (CH) Index
| Clustering Method | CH Score |
|-------------------|----------:|
| **Hierarchical** | **97.2782** |
| K-Means | 86.7430 |
| DBSCAN | 78.5664 |

### 🧩 Davies–Bouldin Index (DBI)
| Clustering Method | DBI |
|-------------------|-----:|
| **Hierarchical** | **0.8194** |
| DBSCAN | 1.0093 |
| K-Means | 3.4313 |

---

## 🔍 Observations
- **Hierarchical Clustering** achieved the highest **Separation/Spread ratio (2.44)** and **CH Index (97.27)**, along with the lowest **DBI (0.82)**, indicating compact and well-separated clusters.  
- **DBSCAN** closely followed, effectively handling noise and outliers but slightly less cohesive.  
- **K-Means** showed higher intra-cluster variation, likely due to sensitivity to initialization and spherical cluster assumptions.  

Overall, **Hierarchical Clustering** was found to be the most robust and effective clustering method for this dataset.

---

## 🧠 Key Insights
- Dimensionality reduction using **PCA** significantly improved computational efficiency and interpretability.  
- Implementing metrics **from scratch** provided a deeper understanding of clustering evaluation.  
- Consistent metric performance across methods validated the robustness of the evaluation pipeline.

---

## 💻 Technologies Used
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

## ⚙️ Dependencies and Requirements

### 🧩 Python Environment
The project requires **Python 3.10+** and can be run seamlessly on **Google Colab** or **Jupyter Notebook**.

### 📦 Installation
Install the required dependencies before running any notebook:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

---

## 🧾 Conclusion
- **Hierarchical Clustering** produced the most meaningful and interpretable customer groups.  
- **DBSCAN** effectively identified arbitrary shapes and noise, though parameter-sensitive.  
- **K-Means** performed adequately but was less suitable for the dataset's structure.  
- These results highlight that **no single clustering method fits all datasets**—the choice must align with data distribution, density, and business objectives.

---

## 👩‍💻 Authors
**Prapti Halder (M25CSA022)**  
**Layaa Vishwakarma (M25CSA017)**  
**Suparni Maitra (M25CSA029)**  

📍 *Course: CSL7620 – Machine Learning (Semester I)*  
📅 *November 2025*  
🏫 *Indian Institute of Technology Jodhpur*

---
