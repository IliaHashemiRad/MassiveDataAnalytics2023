# Similar News Detection

## 📖 Overview

This project implements an efficient duplicate and near-duplicate detection system for Persian news articles using Locality-Sensitive Hashing (LSH). The system scales to handle large news corpora by reducing the comparison space from O(n²) to a manageable set of candidate pairs.

## 🎯 Objectives

- Detect similar and duplicate news articles in large-scale datasets
- Implement scalable similarity detection using LSH techniques
- Minimize computational complexity while maintaining high accuracy
- Handle Persian text with appropriate preprocessing

## 🔧 Technologies Used

- **Apache Spark (RDD API):** For distributed processing
- **PySpark:** Python interface for Spark
- **Custom Hash Functions:** For min-hashing implementation
- **JSON Processing:** For handling structured news data

## 📊 Key Features

### 1. **Shingling**
- Converts documents into 2-word shingles (bi-grams)
- Removes stop words before shingle creation
- Creates compact document representations
- Preserves local word order information

### 2. **Min-Hashing**
- Generates compact signatures for documents
- Uses 120 hash functions (40 bands × 3 rows per band)
- Reduces high-dimensional shingle sets to fixed-size signatures
- Preserves Jaccard similarity properties

### 3. **Locality-Sensitive Hashing (LSH)**
- Groups documents by hash bands
- Identifies candidate pairs efficiently
- Reduces comparison space dramatically
- Configurable threshold for similarity detection

### 4. **Similarity Computation**
- Calculates exact Jaccard similarity for candidate pairs
- Threshold-based filtering for final results
- Validates LSH candidates with actual similarity scores
- Reports similar document pairs with similarity scores

## 📁 Files

- **MDA2023-HW2.ipynb:** Main Jupyter notebook with complete implementation
- **Report.pdf:** Detailed project report with methodology and results
- **persian.txt:** Persian stop words list
- **verbal.txt:** Verbal stop words
- **nonverbal.txt:** Non-verbal stop words
- **chars.txt:** Character list for text processing
- **short.txt:** Short word list

## 🚀 Getting Started

### Prerequisites
```bash
pip install pyspark
```

### Running the Project

1. Open the Jupyter notebook:
```bash
jupyter notebook MDA2023-HW2.ipynb
```

2. Ensure the Persian news dataset is available in JSON format

3. Run all cells sequentially to perform similarity detection

## 🔍 Algorithm Details

### Shingling
```
Input: Document text
Process:
  1. Remove stop words
  2. Create 2-word sliding windows
  3. Generate shingle set
Output: Set of bi-gram shingles
```

### Min-Hashing
```
Input: Shingle set
Process:
  1. Apply 120 hash functions
  2. Take minimum hash value for each function
  3. Create signature vector
Output: Fixed-size signature (120 elements)
```

### LSH
```
Input: Signatures
Process:
  1. Divide signatures into 40 bands of 3 rows
  2. Hash each band
  3. Group documents with matching band hashes
  4. Generate candidate pairs
Output: Candidate similar pairs
```

### Jaccard Similarity
```
Input: Two shingle sets S1, S2
Formula: J(S1, S2) = |S1 ∩ S2| / |S1 ∪ S2|
Output: Similarity score [0, 1]
```

## 📈 Performance

- **Efficiency:** Reduces comparisons from O(n²) to O(c) where c is number of candidate pairs
- **Accuracy:** LSH parameters tuned to balance false positives and false negatives
- **Scalability:** Handles large news corpora through distributed processing
- **Speed:** Significantly faster than brute-force pairwise comparison

## 💡 Key Insights

- LSH dramatically reduces computational requirements for similarity detection
- Band/row configuration (40 bands × 3 rows) balances precision and recall
- Min-hashing preserves similarity while reducing dimensionality
- Effective for duplicate detection in news aggregation systems

## 🎯 Use Cases

- News aggregation platforms
- Duplicate content detection
- Plagiarism detection
- Content recommendation systems
- Data deduplication pipelines

## 📚 Further Reading

For detailed methodology, algorithm explanations, experimental results, and performance analysis, please refer to **Report.pdf**.

---

*This project demonstrates efficient large-scale similarity detection using advanced hashing techniques.*
