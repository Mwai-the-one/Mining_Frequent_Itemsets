# Mining Frequent Itemsets: Closed vs. Maximal

**Course:** Data Mining / Warehousing
**Assignment:** Exploring Frequent Itemsets in Supermarket Data
**Group:** [Insert Group Number, e.g., Group 05]

---

## 1. Project Overview
This project simulates a large-scale supermarket transaction dataset to analyze purchasing patterns. By applying the **Apriori algorithm**, we identify associations between products. The primary objective is to demonstrate the computational differences and relationships between three categories of itemsets:

1.  **Frequent Itemsets:** Itemsets that appear in the dataset with a frequency no less than a user-specified threshold (Min Support).
2.  **Closed Frequent Itemsets:** A frequent itemset is "closed" if there exists no superset that has the same support count. (This is a lossless compression of frequent itemsets).
3.  **Maximal Frequent Itemsets:** A frequent itemset is "maximal" if none of its immediate supersets are frequent. (This is a lossy compression).

## 2. Team Contributors
**Roles & Responsibilities:**
The workload was distributed to ensure every member contributed to code logic and documentation.

| Name | Email | Primary Contribution |
|------|-------|----------------------|
| **[Student A]** | [Email] | **Data Generation:** Implemented the simulation logic to create 3000+ random transactions from a pool of unique items. |
| **[Peter Kidiga]** | [Email] | **Preprocessing & Apriori:** Handled One-Hot Encoding using `TransactionEncoder` and generated the base frequent itemsets. |
| **[Student C]** | [Email] | **Closed Itemsets Logic:** Developed the algorithm to filter frequent itemsets to identify those that are Closed. |
| **[Student D]** | [Email] | **Maximal Itemsets Logic:** Developed the algorithm to filter frequent itemsets to identify those that are Maximal. |

---

## 3. Technical Approach & Methodology

### Step 1: Data Simulation
We utilized Python's `random` library to generate a synthetic dataset mimicking a supermarket environment.
* **Transactions:** 3,000
* **Item Pool:** 32 unique items (e.g., Milk, Bread, Diapers)
* **Basket Size:** Randomized between 2 and 7 items per transaction.

### Step 2: Preprocessing
The raw list of transactions was converted into a **One-Hot Encoded** boolean matrix using `mlxtend.preprocessing.TransactionEncoder`.
* Rows represent transactions.
* Columns represent items.
* Values are `True`/`False` (bought/not bought).

### Step 3: Association Rule Mining (Apriori)
We used the `mlxtend.frequent_patterns.apriori` function.
* **Minimum Support:** `0.05` (5%). This means an itemset must appear in at least 150 of the 3,000 transactions to be considered relevant.

### Step 4: Filtering Logic
* **Finding Closed Itemsets:** We iterated through the frequent itemsets to check if any superset existed with the *exact same support value*. If not, the itemset is Closed.
* **Finding Maximal Itemsets:** We iterated through the frequent itemsets to check if *any frequent superset* existed at all. If not, the itemset is Maximal.

---

## 4. Repository Structure & File Descriptions

```text
├── README.md                       # Project documentation and group details
├── frequent_itemsets_analysis.ipynb # MAIN SCRIPT: Contains all code, comments, and logic
├── supermarket_transactions.csv    # RAW DATA: The 3,000 simulated transactions
├── frequent_itemsets.csv           # OUTPUT: All itemsets with support > 0.05
├── closed_itemsets.csv             # OUTPUT: Subset of itemsets that are Closed
└── maximal_itemsets.csv            # OUTPUT: Subset of itemsets that are Maximal
```
This detailed version expands on the technical methodology, installation instructions, and file descriptions. It is designed to look professional on GitHub and demonstrates a deeper understanding of the assignment to your grader.

You can copy the raw markdown below and paste it directly into your README.md file.

Markdown

# Mining Frequent Itemsets: Closed vs. Maximal

**Course:** Data Mining / Warehousing
**Assignment:** Exploring Frequent Itemsets in Supermarket Data

---

## 1. Project Overview
This project simulates a large-scale supermarket transaction dataset to analyze purchasing patterns. By applying the **Apriori algorithm**, we identify associations between products. The primary objective is to demonstrate the computational differences and relationships between three categories of itemsets:

1.  **Frequent Itemsets:** Itemsets that appear in the dataset with a frequency no less than a user-specified threshold (Min Support).
2.  **Closed Frequent Itemsets:** A frequent itemset is "closed" if there exists no superset that has the same support count. (This is a lossless compression of frequent itemsets).
3.  **Maximal Frequent Itemsets:** A frequent itemset is "maximal" if none of its immediate supersets are frequent. (This is a lossy compression).

## 2. Team Contributors
**Roles & Responsibilities:**
The workload was distributed to ensure every member contributed to code logic and documentation.

| Name | Email | Primary Contribution |
|------|-------|----------------------|
| **[Student A]** | [Email] | **Data Generation:** Implemented the simulation logic to create 3000+ random transactions from a pool of unique items. |
| **[Student B]** | [Email] | **Preprocessing & Apriori:** Handled One-Hot Encoding using `TransactionEncoder` and generated the base frequent itemsets. |
| **[Student C]** | [Email] | **Closed Itemsets Logic:** Developed the algorithm to filter frequent itemsets to identify those that are Closed. |
| **[Student D]** | [Email] | **Maximal Itemsets Logic:** Developed the algorithm to filter frequent itemsets to identify those that are Maximal. |

---

## 3. Technical Approach & Methodology

### Step 1: Data Simulation
We utilized Python's `random` library to generate a synthetic dataset mimicking a supermarket environment.
* **Transactions:** 3,000
* **Item Pool:** 32 unique items (e.g., Milk, Bread, Diapers)
* **Basket Size:** Randomized between 2 and 7 items per transaction.

### Step 2: Preprocessing
The raw list of transactions was converted into a **One-Hot Encoded** boolean matrix using `mlxtend.preprocessing.TransactionEncoder`.
* Rows represent transactions.
* Columns represent items.
* Values are `True`/`False` (bought/not bought).

### Step 3: Association Rule Mining (Apriori)
We used the `mlxtend.frequent_patterns.apriori` function.
* **Minimum Support:** `0.05` (5%). This means an itemset must appear in at least 150 of the 3,000 transactions to be considered relevant.

### Step 4: Filtering Logic
* **Finding Closed Itemsets:** We iterated through the frequent itemsets to check if any superset existed with the *exact same support value*. If not, the itemset is Closed.
* **Finding Maximal Itemsets:** We iterated through the frequent itemsets to check if *any frequent superset* existed at all. If not, the itemset is Maximal.

---

## 4. Repository Structure & File Descriptions

```text
├── README.md                       # Project documentation and group details
├── frequent_itemsets_analysis.ipynb # MAIN SCRIPT: Contains all code, comments, and logic
├── supermarket_transactions.csv    # RAW DATA: The 3,000 simulated transactions
├── frequent_itemsets.csv           # OUTPUT: All itemsets with support > 0.05
├── closed_itemsets.csv             # OUTPUT: Subset of itemsets that are Closed
└── maximal_itemsets.csv            # OUTPUT: Subset of itemsets that are Maximal
## 5. Installation & Usage
To run this project locally, ensure you have Python installed.

Prerequisites
You need the pandas library for data handling and mlxtend for the mining algorithms.

Bash

pip install pandas numpy mlxtend
Running the Code
Clone this repository.

Open frequent_itemsets_analysis.ipynb in Jupyter Notebook, JupyterLab, or VS Code.

Run all cells in order.

The script will generate the .csv files in your current directory.

## 6. Sample Results
Below is a snippet of the logic output structure:

Top Frequent Itemsets: | Support | Itemsets | |:-------:|:---------| | 0.15 | (Milk) | | 0.12 | (Bread) |

Counts:

Total Frequent Itemsets: [Number generated by script]

Total Closed Itemsets: [Number generated by script]

Total Maximal Itemsets: [Number generated by script]

## 7. Acknowledgments
Library used: Mlxtend (Machine Learning Extensions)

Course: Data Mining / Warehousing
