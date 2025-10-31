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

## ⚙️ Workflow of the Project
### 1. **Data Preprocessing**
- **Handling Missing Values:** Removed or imputed missing entries using median (numeric) and mode (categorical).  
- **Encoding Categorical Data:** Converted categorical variables into numerical format.  
- **Dimensionality Reduction:** Applied **Principal Component Analysis (PCA)** to reduce dimensionality, remove noise, and retain maximum variance.

### 2. **Data Clustering**
Three clustering algorithms were implemented **from scratch**:

| Algorithm | Description |
|------------|-------------|
| **K-Means Clustering** | Iterative partitioning into *k* clusters using K-Means++ initialization. Optimal *k* determined via hybrid Elbow–Silhouette method. |
| **Hierarchical Clustering** | Built using Ward’s linkage and visualized with a dendrogram. Optimal *k* obtained using silhouette analysis. |
| **DBSCAN** | Implemented manually with custom Epsilon (eps) and MinPts selection using k-distance graph and grid search. |

### 3. **Evaluation of Techniques**
Each clustering result was assessed using:
- **Separation / Spread Ratio:** Custom metric comparing cluster separation vs. compactness.  
- **Calinski–Harabasz (CH) Index:** Higher score = more distinct clusters.  
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
- **Hierarchical Clustering** achieved the highest **Separation/Spread ratio** (2.44) and **CH Index** (97.27), along with the lowest **DBI** (0.82), indicating the most compact and well-separated clusters.  
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

## 🧾 Conclusion
- **Hierarchical Clustering** produced the most meaningful and interpretable customer groups.  
- **DBSCAN** effectively identified arbitrary shapes and noise, though parameter-sensitive.  
- **K-Means** performed adequately but was less suitable for the dataset’s structure.  
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

