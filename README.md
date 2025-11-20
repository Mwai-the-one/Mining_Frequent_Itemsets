📦 Supermarket Transaction Mining Project
Frequent, Closed, and Maximal Itemset Generation Using the Apriori Algorithm


📘 Project Overview
This project demonstrates a complete workflow for market basket analysis using simulated supermarket transaction data.
It covers:

Synthetic data generation for 3,000 supermarket transactions

Preprocessing via one-hot encoding

Frequent itemset mining using Apriori

Identification of Closed Frequent Itemsets

Identification of Maximal Frequent Itemsets

Saving full results to CSV

The work was collaboratively completed by group members (A–E) as part of a Data Mining practical assignment.


🧰 Technologies & Libraries Used

Purpose	                                     Library
Data manipulation	                           pandas,numpy
Randomized simulations	                     random
Transaction encoding	                       mlxtend.preprocessing.TransactionEncoder
Frequent itemset mining	                     mlxtend.frequent_patterns.apriori


📂 Project Structure

├── supermarket_transactions.csv          # Raw simulated transactions
├── frequent_itemsets.csv                 # All frequent itemsets (support ≥ 0.05)
├── closed_itemsets.csv                   # Closed frequent itemsets
├── maximal_itemsets.csv                  # Maximal frequent itemsets
└── mining_script.py                      # Main Python script for mining

🧾 Step-by-Step Explanation of the Code


🧑‍🎓 1. Import Libraries
Handles data manipulation, random sampling, encoding, and mining.


🛒 2. Simulating Supermarket Transaction Data

✔️ Item Pool
A list of 30+ unique supermarket items is created (milk, bread, meat, beverages, toiletries, etc.).

✔️ Transaction Generation
3,000 transactions are generated.
Each transaction contains 2 to 7 random items, sampled without replacement.
This mimics real-world shopping behavior.


🧼 3. Preprocessing via One-Hot Encoding

This produces a DataFrame where:
Each row = a transaction
Each column = an item
Each cell = True/False indicating presence
Example:

Milk	Bread	Eggs	Soda	
True	False	True	False


📊 4. Frequent Itemset Mining (Apriori Algorithm)

✔️ Applying Apriori
A support threshold of 0.05 (5%) is used.

✔️ Itemset Length
We record the number of items in each itemset.
✔️ Sorting & Saving

We sort by support (highest first), then save.
Example record:

itemsets	support	length
{Bread}	0.41	1


🔐 5. Closed Frequent Itemsets

⭐ Definition

An itemset X is closed if:
No strict superset of X has the same support.
This helps remove redundant itemsets.

✔️ Implementation Logic
For each frequent itemset:
Compare it with every other itemset.
Check if any superset shares identical support.
If yes → Not Closed
If no → Closed


🏆 6. Maximal Frequent Itemsets

⭐ Definition

An itemset X is maximal if:
It has no frequent superset at all.
Maximal itemsets are the most concise summary of frequent patterns.

✔️ Implementation Logic

For each frequent itemset:
Check if there exists any strict superset.
If none exist → itemset is maximal.


📁 Generated Output Files

| File                           | Description                         |
| ------------------------------ | ----------------------------------- |
| `supermarket_transactions.csv` | All 3000 raw synthetic transactions |
| `frequent_itemsets.csv`        | All frequent itemsets ≥ 5% support  |
| `closed_itemsets.csv`          | Closed frequent itemsets            |
| `maximal_itemsets.csv`         | Maximal frequent itemsets           |


🎉 Conclusion

This project successfully demonstrates:
How to simulate realistic shopping data
How to preprocess data for association mining
How Apriori can extract valuable frequent patterns
Identification of frequent, closed, and maximal itemsets
Proper data export for analysis or reporting
It represents a full end-to-end Market Basket Analysis workflow suitable for coursework, research, or industry prototyping.
