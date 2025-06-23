# 💊 Drugs Repositioning with Machine Learning 💡
![K-Means](https://github.com/VicDc/Drugs-Repositioning/blob/6a325228eb1a7957ccd98d26d5e2398f51a81dda/img_Drugs/1750604649726.jpg)
Welcome to the **Drugs Repositioning** project repository! This project explores the fascinating field of repurposing existing drugs for new therapeutic uses, leveraging the power of Machine Learning. By identifying novel connections between drugs and diseases, we aim to accelerate drug discovery, reduce development costs, and bring new treatments to patients faster.

## 🤔 What is Drug Repositioning?

Drug repositioning (also known as drug repurposing or reprofiling) is the process of identifying new therapeutic uses for existing drugs. Instead of developing a new drug from scratch, which is incredibly costly and time-consuming, this strategy looks for hidden potentials in compounds already approved for other conditions.

Imagine a drug approved for diabetes, but it might also be effective against a certain type of cancer! 🤯 This approach is efficient because:
* **Lower Risk:** Known safety profiles of existing drugs.
* **Faster Development:** Bypass lengthy early-stage trials.
* **Reduced Costs:** Significant savings compared to de novo drug discovery.

This repository showcases two distinct Machine Learning approaches applied to drug repositioning: an unsupervised clustering method (K-means) and a supervised classification method (Random Forest).

---

## Part 1: 📊 Uncovering Patterns with K-means Clustering

This section focuses on an **exploratory, unsupervised analysis** using K-means clustering to discover natural groupings and hidden patterns within drug-disease associations based on their textual similarities. This approach helps in generating new hypotheses for drug repositioning.

### 🚀 Workflow & Key Steps:

1.  **Data Acquisition & Preparation:**
    * Loading and merging comprehensive datasets (`mapping.csv`, `drugsInfo.csv`, `diseasesInfo.csv`) containing detailed information on drug-disease associations.
    * Cleaning and structuring the data for analysis.
2.  **Text Vectorization (TF-IDF):**
    * Converting textual descriptions (drug/disease names, descriptions, mechanisms, symptoms, etc.) into numerical vectors using `TfidfVectorizer`. This process captures the semantic importance of words.
3.  **Dimensionality Reduction (PCA):**
    * Applying Principal Component Analysis (`PCA`) to reduce the high dimensionality of the TF-IDF vectors, making the data more manageable for clustering and visualization.
4.  **Optimal Cluster Determination (Elbow Method):**
    * Utilizing the Elbow Method to identify the most appropriate number of clusters (`k`) for the K-means algorithm, ensuring meaningful groupings. In our analysis, **10 optimal clusters** were identified. 🎯
5.  **K-means Clustering:**
    * Applying the `KMeans` algorithm to group drug-disease associations into the optimal number of clusters based on their similarity.
6.  **Semantic Analysis of Clusters:**
    * For each of the **10 identified clusters**, we extract and analyze:
        * **Top Keywords:** Up to 15 most representative terms defining the cluster's "theme" (e.g., "pain," "inflammation," "cancer").
        * **Example Drugs:** Top 5 most common drugs within the cluster.
        * **Example Diseases:** Top 5 most common diseases within the cluster.
    * This analysis helps in generating data-driven hypotheses for potential new drug applications. 💡

### 📦 Technologies Used:
`Python`, `pandas`, `numpy`, `scikit-learn`, `matplotlib`

### 🔗 Notebook:
[DrugsRepositioning_K-means_EN.ipynb](https://github.com/VicDc/Drugs-Repositioning/blob/main/DrugsRepositioning_K-means_EN.ipynb)

---

## Part 2: 🎯 Predicting New Uses with Random Forest Classification

This section explores a **supervised learning approach** using a Random Forest Classifier to predict novel relationships between existing drugs and diseases. The goal is to accelerate the discovery of new therapies by building a robust predictive model.

### 🚀 Workflow & Key Steps:

1.  **Data Integration & Feature Engineering:**
    * Combining comprehensive drug and disease data into a single, rich dataset.
    * Creating combined textual features from `DrugName`, `DrugDescription`, `DiseaseName`, `DiseaseDescription`, and other relevant attributes.
2.  **Dataset Balancing (Positive & Negative Samples):**
    * Constructing a balanced dataset by combining **42,200 positive samples** (known drug-disease associations) with **42,200 randomly generated negative samples** (non-associations), totaling **84,400 samples**. This ensures the model learns effectively from both existing and non-existing relationships. ⚖️
3.  **Text Vectorization (TF-IDF):**
    * Utilizing `TfidfVectorizer` to transform the combined textual features into numerical vectors, suitable for machine learning algorithms.
4.  **Model Training (Random Forest):**
    * Splitting the dataset into training and testing sets.
    * Training a powerful `RandomForestClassifier` on the vectorized data to learn the complex patterns indicative of drug-disease associations.
5.  **Model Evaluation:**
    * Assessing the performance of the trained model using standard classification metrics.
    * The model achieved remarkable results:
        * **Accuracy: 92%** 🏆
        * **Precision: 92%**
        * **Recall: 92%**
        * **F1-Score: 92%**
6.  **Prediction & Visualization:**
    * Using the trained model to predict new, high-probability drug-disease associations.
    * Visualizing these predictions via an interactive **Force Layout Graph**, allowing exploration of potential new therapeutic connections. 🌐

### 📦 Technologies Used:
`Python`, `pandas`, `numpy`, `scikit-learn`

### 🔗 Notebook:
[drug_repositioning_randomforest_v4_en.ipynb](https://github.com/VicDc/Drugs-Repositioning/blob/main/drug_repositioning_randomforest_v4_en.ipynb)

---

## 👨‍💻 Get Started:

To explore the notebooks:
1.  Clone this repository: `git clone https://github.com/YourUsername/Drugs-Repositioning.git`
2.  Navigate to the directory: `cd Drugs-Repositioning`
3.  Open the notebooks with Jupyter Lab/Notebook or Google Colab.

Feel free to explore, fork, and contribute! Your feedback and suggestions are welcome. ✨

---
