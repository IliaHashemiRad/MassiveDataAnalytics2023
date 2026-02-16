# Data Analytics - Persian News Dataset

## 📖 Overview

This project performs comprehensive exploratory data analysis on a large-scale Persian (Farsi) news dataset using Apache Spark's distributed computing capabilities. The analysis includes text preprocessing, frequent pattern mining, and statistical visualization tailored for Persian language content.

## 🎯 Objectives

- Analyze and explore a large corpus of Persian news articles using distributed computing
- Implement text preprocessing pipelines for Persian language
- Apply frequent itemset mining algorithms to discover common word patterns
- Generate insights through statistical analysis and visualizations

## 🔧 Technologies Used

- **Apache Spark (RDD API):** For distributed data processing
- **PySpark:** Python interface for Spark
- **Matplotlib:** Statistical visualizations
- **WordCloud:** Persian text visualization
- **NLTK:** Natural language processing utilities
- **Custom Persian text processing libraries**

## 📊 Key Features

### 1. **Data Preparation**
- JSON parsing and data loading
- Data partitioning for distributed processing
- Dataset structure analysis

### 2. **Text Preprocessing**
- Persian text cleaning (special characters, Unicode artifacts removal)
- Stop word removal using custom Persian stop word lists
- Digit and punctuation filtering
- Character encoding normalization

### 3. **Exploratory Analysis**
- Finding longest news articles
- Word frequency analysis
- Top 20 most frequent words identification
- Document length distribution

### 4. **Frequent Itemset Mining**
- **SON Algorithm:** Sarawagi-Omiecinski-Naughton algorithm for distributed frequent itemset mining
- **A-Priori Algorithm:** Classic association rule mining
- Discovery of frequently co-occurring word combinations
- Support threshold configuration

### 5. **Visualization**
- Word frequency distribution plots
- WordCloud generation with Persian font support
- Statistical charts and graphs

## 📁 Files

- **MDA2023-HW1.ipynb:** Main Jupyter notebook with complete implementation
- **news.ipynb:** Additional news analysis notebook
- **Tweets_new.ipynb:** Extended analysis notebook
- **Report.pdf:** Detailed project report with methodology and results
- **Proj.pdf:** Project specifications

## 🚀 Getting Started

### Prerequisites
```bash
pip install pyspark matplotlib nltk wordcloud
```

### Running the Project

1. Open the Jupyter notebook:
```bash
jupyter notebook MDA2023-HW1.ipynb
```

2. Ensure you have access to the Persian news dataset (JSON format)

3. Run all cells sequentially to reproduce the analysis

## 📈 Results

The analysis provides:
- Statistical insights about the Persian news corpus
- Most frequent words and their distributions
- Common word patterns and associations
- Visual representations of text data

## 🔍 Algorithms Implemented

### SON Algorithm
Distributed frequent itemset mining that works in two phases:
1. **Map Phase:** Find locally frequent itemsets in each partition
2. **Reduce Phase:** Count global frequency of candidate itemsets

### A-Priori Algorithm
Classic algorithm for mining frequent itemsets:
- Generates candidate itemsets iteratively
- Uses downward closure property
- Prunes infrequent candidates

## 💡 Key Insights

- Demonstrates scalability of Spark RDD for large text datasets
- Shows effectiveness of distributed algorithms for pattern mining
- Highlights challenges in Persian text processing
- Provides reusable patterns for text analytics in non-English languages

## 📚 Further Reading

For detailed methodology, algorithm explanations, and comprehensive results, please refer to **Report.pdf**.

---

*This project demonstrates practical application of massive data analytics techniques for natural language processing in Persian.*
