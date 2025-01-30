# 🏗️ Text Clustering using K-Means

## 📜 Overview  
This project performs **unsupervised clustering** on a subset of the **20 Newsgroups dataset**, which contains **2,500 documents** belonging to one of five categories:  
- `0` - Windows  
- `1` - Cryptography  
- `2` - Christianity  
- `3` - Hockey  
- `4` - For Sale  
Each document is represented as a **sparse term-document matrix** with **9,328 unique terms** (stems). The goal is to apply **K-Means clustering**, analyze cluster characteristics, and compare clustering results to the original categories.  

## 🎯 Problem Explanation  
The project includes the following key tasks:  
1. **Implement a custom Cosine similarity distance function** for K-Means.  
2. **Preprocess the dataset** (transpose term-document matrix, random train-test split, and TF-IDF transformation).  
3. **Perform K-Means clustering** on the transformed dataset using different values of K (from **4 to 8**) and analyze cluster properties.  
4. **Evaluate cluster quality** using **Completeness and Homogeneity scores**.  
5. **Classify new documents** from the test set based on **Cosine similarity to cluster centroids**.  
6. **Generate Word Clouds** for each cluster.  

## 🛠️ Implementation Details  
### **1. Custom Cosine Similarity Distance Function**  
- K-Means normally uses **Euclidean distance**, but for text data, **Cosine similarity** is more effective.  
- A custom distance function is implemented that computes: Cosine Distance = 1 - Cosine Similarity
### 2. Data Preprocessing
- Transpose the term-document matrix (documents as rows, terms as columns).
- Randomly split the dataset into: 80% training data (used for clustering) and 20% test data (used for classification).
- Apply TF-IDF transformation to the data.
### 3. K-Means Clustering
- Run K-Means clustering on the training data for different values of K (4 to 8).
- Experiment with multiple random initializations to identify the best clustering structure.
- Extract top N terms per cluster based on:
Cluster Document Frequency (DF): Percentage of docs in the cluster containing a term.
Centroid TF-IDF Weight: Mean TF-IDF weight of the term in the cluster.
- The final results summarize which terms define each cluster.
### 4. Clustering Evaluation
- Compute Completeness and Homogeneity scores to measure clustering quality.
- Higher scores indicate better alignment between clusters and true labels.
- Experiment with different values of K to find the optimal number of clusters.
### 5. Classifying Test Data Using Cosine Similarity
- Assign each document in the test set to the closest cluster centroid based on Cosine similarity.
- Output predicted cluster label and similarity score for each document.
### 6. Word Cloud Generation
- Create word clouds for each cluster to visually represent important terms.

### 🚀 Technologies Used
- **Python** (for text processing and clustering).
- **NumPy & Pandas** (for data manipulation).
- **Scikit-learn** (for TF-IDF transformation and clustering evaluation).
- **Matplotlib & Seaborn** (for visualizing cluster statistics).
- **WordCloud** (for generating cluster word clouds).
