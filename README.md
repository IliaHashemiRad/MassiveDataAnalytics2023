# Massive Data Analytics 2023

[![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.x-E25A1C?logo=apache-spark&logoColor=white)](https://spark.apache.org/)
[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)

A comprehensive collection of distributed data analytics projects using Apache Spark and advanced machine learning algorithms. This repository contains implementations of various data mining and recommendation system techniques for large-scale datasets.

## 📋 Overview

This repository showcases practical implementations of massive data analytics techniques applied to real-world datasets, including Persian news articles and Twitter social media data. All projects utilize Apache Spark's RDD API for distributed computing, demonstrating scalability and efficiency in handling large datasets.

## 🗂️ Projects

### 1. [Data Analytics](./Data%20Analytics/)
**Exploratory Data Analysis on Persian News Dataset**

Comprehensive analysis of Persian (Farsi) news articles using distributed computing techniques:
- Text preprocessing and cleaning for Persian language
- Frequent itemset mining using SON and A-Priori algorithms
- Statistical analysis and visualization
- Word frequency analysis with custom Persian font support

**Key Technologies:** Apache Spark RDD, PySpark, Matplotlib, WordCloud, NLTK

---

### 2. [Similar News Detection](./Similar%20News%20Detection/)
**Document Similarity Detection Using LSH**

Scalable duplicate detection system for identifying similar news articles:
- Shingling and min-hashing techniques
- Locality-Sensitive Hashing (LSH) for efficient similarity detection
- Jaccard similarity computation
- Handles large-scale Persian news corpus

**Key Technologies:** Apache Spark RDD, PySpark, Custom hash functions

---

### 3. [Twitter Recommendation System](./Twitter%20Recommendation%20System/)

#### 3.1 [Collaborative Filtering](./Twitter%20Recommendation%20System/Collaborative%20filtering/)
**User-Based Collaborative Filtering for Tweet Recommendations**

Recommendation engine based on user similarity:
- User-tweet interaction matrix construction
- K-Nearest Neighbors (KNN) algorithm
- Weighted average predictions
- Rating system based on retweets, replies, and quotes

**Key Technologies:** Apache Spark RDD, PySpark, Collaborative filtering algorithms

#### 3.2 [Random Walk with Restart](./Twitter%20Recommendation%20System/Random%20Walk%20with%20Restart/)
**Graph-Based Tweet Recommendations Using RWR**

Graph-based approach to discovering similar users and recommending content:
- User interaction graph construction
- Random Walk with Restart (RWR) algorithm
- Visit frequency analysis for similarity computation
- Comparative analysis with standard random walk

**Key Technologies:** Apache Spark RDD, PySpark, Graph algorithms

---

## 🛠️ Technologies & Tools

- **Apache Spark:** Distributed computing framework (RDD API)
- **Python:** Primary programming language
- **PySpark:** Python API for Spark
- **Jupyter Notebooks:** Interactive development environment
- **Libraries:** NLTK, Matplotlib, WordCloud, and custom implementations

## 📊 Datasets

- **Persian News Dataset:** Collection of Farsi news articles in JSON format
- **Twitter Dataset:** Social media interaction data including tweets, retweets, replies, and quotes

## 🚀 Getting Started

### Prerequisites

```bash
# Python 3.x
# Apache Spark 3.x
# Jupyter Notebook
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/IliaHashemiRad/MassiveDataAnalytics2023.git
cd MassiveDataAnalytics2023
```

2. Install required Python packages:
```bash
pip install pyspark jupyter matplotlib nltk wordcloud
```

3. Start Jupyter Notebook:
```bash
jupyter notebook
```

4. Navigate to any project folder and open the respective `.ipynb` file

## 📝 Project Structure

```
MassiveDataAnalytics2023/
├── Data Analytics/
│   ├── MDA2023-HW1.ipynb       # Main notebook
│   ├── Report.pdf               # Detailed report
│   └── README.md
├── Similar News Detection/
│   ├── MDA2023-HW2.ipynb       # Main notebook
│   ├── Report.pdf               # Detailed report
│   ├── persian.txt              # Persian stop words
│   └── README.md
└── Twitter Recommendation System/
    ├── Collaborative filtering/
    │   ├── MDA2023-HW3.ipynb   # Main notebook
    │   ├── Report.pdf           # Detailed report
    │   └── README.md
    └── Random Walk with Restart/
        ├── MDA2023-HW4.ipynb   # Main notebook
        ├── Report.pdf           # Detailed report
        └── README.md
```

## 📚 Learning Outcomes

This repository demonstrates proficiency in:
- Distributed data processing with Apache Spark
- Text mining and natural language processing for Persian text
- Similarity detection algorithms (LSH, Min-Hashing, Jaccard)
- Recommendation systems (Collaborative Filtering, Graph-based methods)
- Frequent pattern mining (A-Priori, SON algorithm)
- Graph algorithms (Random Walk with Restart)
- Large-scale data visualization

## 📖 Documentation

Each project folder contains:
- **Jupyter Notebook (.ipynb):** Complete implementation with code and explanations
- **Report (PDF):** Detailed analysis, methodology, and results
- **README.md:** Project-specific documentation and instructions

## 🤝 Contributing

This is an academic project repository. For suggestions or improvements, please open an issue or submit a pull request.

## 📧 Contact

For questions or collaboration opportunities, please reach out through GitHub issues.

## 📄 License

This project is available for educational purposes. Please check individual project folders for specific licensing information.

---

*Part of Massive Data Analytics Course 2023*
