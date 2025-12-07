# 🏴󠁧󠁢󠁳󠁣󠁴󠁿 Scottish Haggis Evolutionary Analysis

### A Data Mining Investigation into the Morphology of *Haggis scoticus*

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Status](https://img.shields.io/badge/Status-Complete-green)

## 📖 Project Overview
This project involves a comprehensive data mining investigation commissioned by the fictional wildlife pioneer **Lord Ramsay McCraig**. The objective was to analyze a dataset of 344 distinct Haggis sightings across three Scottish islands (Skye, Iona, Shetland) to classify species and understand their morphological differences.

Using the full **Data Mining Lifecycle**, this project moves from raw data cleaning to advanced unsupervised clustering, supervised classification, and linear regression.

## 📊 The Dataset
The dataset contains morphological measurements and metadata for three alleged subspecies:
* **Wild Rambler** (Large, long-tailed)
* **Macduff** (Small, short-nosed)
* **Bog Sniffler** (Transitional, long-nosed)

**Features analyzed:** `nose_length_mm`, `tail_length_mm`, `eye_size_mm`, `body_mass_g`, `sex`, `island`, and `year`.

## 🛠️ Methodology & Stages

### Stage 1: Data Preparation & EDA
* **Cleaning:** Handled data entry errors (e.g., removing records where sex was listed as 'green') and missing biometric data.
* **EDA:** Visualized feature distributions, revealing a clear bimodal distribution in body mass and strong multicollinearity between tail length and mass.

### Stage 2: Unsupervised Learning (Clustering)
* **K-Means:** Determined optimal $k=3$ using Elbow and Silhouette analysis, confirming that biological traits naturally group into three distinct clusters without prior labeling.
* **DBSCAN (Advanced):** Identified a high noise ratio (~57%) in the boundary between *Macduff* and *Bog Sniffler*, suggesting these two species form a **continuous morphological gradient** or "hybrid zone," unlike the distinct *Wild Rambler*.

### Stage 3: Supervised Classification (Decision Trees)
* Implemented **Decision Trees**, **Random Forests**, and **Cost-Complexity Pruning**.
* **Rule Extraction:** Derived human-readable identification rules for field biologists.
    * *Example Rule:* `IF nose_length > 42mm AND location == Shetland THEN Bog Sniffler`.

### Stage 4: Comparative Analysis (KNN & Logistic Regression)
* Compared **Decision Trees (84%)**, **Logistic Regression (91%)**, and **K-Nearest Neighbors (92%)**.
* **Conclusion:** KNN outperformed tree-based models, indicating that species boundaries are "smooth" and continuous rather than rigid and orthogonal.

### Stage 5: Regression
* Developed a **Linear Regression** model to predict the body mass of a specimen based on its dimensions.
* Achieved an **$R^2$ of 0.86**, allowing for highly accurate weight estimation in the field based primarily on tail length.

## 🧬 Key Biological Insights
Through this analysis, we discovered several critical biological patterns:
1.  **The "Skye Giant":** The *Wild Rambler* is morphologically distinct from the other two species, characterized by significantly larger body mass (>4.1kg) and tail length.
2.  **The "Iona Exception":** While long-nosed haggis are typically *Bog Snifflers*, our models revealed that on the Island of Iona, long-nosed specimens are genetically/morphologically distinct *Macduffs*, suggesting geographic speciation.
3.  **Sexual Dimorphism:** Logistic regression coefficients indicated distinct morphological variances driven by sex, particularly in eye size distributions.

## 🚀 How to Run
1.  Clone the repository:
    ```bash
    git clone [https://github.com/PedroMarkFernandes/scottish-haggis-analysis.git](https://github.com/PedroMarkFernandes/scottish-haggis-analysis.git)
    ```
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Open the notebook:
    ```bash
    jupyter notebook haggis_analysis.ipynb
    ```

## 📂 Project Structure

```
project_root/
│
├─ haggis-analysis.ipynb # Main analysis notebook
├─ README.md                      # This file
└─ scottish_haggis_2025.csv       # Data
```
