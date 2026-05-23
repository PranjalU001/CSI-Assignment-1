# CSI-Assignment-1
# 🛒 Shopping Dataset Analysis and Cleaning

## 📌 Project Overview

This project focuses on performing **data exploration**, **data cleaning**, and **basic data analysis** using Python and the Pandas library.  
The dataset used in this project contains shopping-related product information collected from multiple CSV files stored inside a ZIP folder.

The main objective of this project is to learn how to:

- Work with datasets using Pandas
- Read and combine multiple CSV files
- Explore dataset structure
- Handle missing values
- Remove duplicate records
- Perform filtering operations
- Create derived columns
- Save cleaned datasets

---

# 🎯 Project Objective

Learn Python basics and perform basic data exploration and cleaning using Pandas.

---

# 📂 Dataset Information

- Dataset Type: Shopping Dataset
- Source: Kaggle
- Dataset Format: ZIP file containing multiple CSV files

Dataset Link:  
https://www.kaggle.com/datasets/anvitkumar/shopping-dataset

---

# 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| Pandas | Data Manipulation and Analysis |
| Zipfile | Extract ZIP files |
| OS Module | File and Directory Operations |
| Glob | Find CSV files recursively |
| Jupyter Notebook | Code Execution and Documentation |

---

# 📦 Libraries Used

```python
import pandas as pd
import zipfile
import os
import glob
```

---

# 🚀 Operations Performed

## 1️⃣ Import Required Libraries

Imported all required Python libraries for:

- Data handling
- ZIP extraction
- File operations
- CSV searching

---

## 2️⃣ Define File Paths

Defined:

- ZIP dataset file name
- Extraction folder path

---

## 3️⃣ Extract ZIP Dataset

Used the `zipfile` module to extract all dataset files from the ZIP archive.

### Operation Performed

```python
with zipfile.ZipFile(zip_file, 'r') as zip_ref:
    zip_ref.extractall(extract_folder)
```

---

## 4️⃣ View Extracted Files

Checked all extracted files and folders using:

```python
os.listdir(extract_folder)
```

---

## 5️⃣ Find All CSV Files

Used the `glob` module to locate all CSV files recursively inside the extracted dataset folder.

### Operation Performed

```python
glob.glob(extract_folder + "/**/*.csv", recursive=True)
```

---

## 6️⃣ Load All CSV Files

Read all CSV files one by one using `pandas.read_csv()` and stored them into a list.

### Operation Performed

```python
df = pd.read_csv(file)
```

---

## 7️⃣ Combine All DataFrames

Merged all individual CSV datasets into one single combined dataset using:

```python
pd.concat()
```

---

## 8️⃣ Save Combined Dataset

Saved the combined dataset into a new CSV file:

```text
combine_shopping_dataset.csv
```

---

# 📊 Data Exploration

The following operations were performed for dataset exploration:

---

## 9️⃣ Display First 5 Rows

```python
combined_df.head()
```

Purpose:
- Preview dataset records

---

## 🔟 Display Last 5 Rows

```python
combined_df.tail()
```

Purpose:
- View ending records of dataset

---

## 1️⃣1️⃣ Check Dataset Shape

```python
combined_df.shape
```

Purpose:
- Find total rows and columns

---

## 1️⃣2️⃣ Display Column Names

```python
combined_df.columns
```

Purpose:
- View dataset features

---

## 1️⃣3️⃣ Check Data Types

```python
combined_df.dtypes
```

Purpose:
- Identify datatype of each column

---

## 1️⃣4️⃣ Display Dataset Information

```python
combined_df.info()
```

Purpose:
- Get complete dataset summary

---

# 🧹 Data Cleaning

## 1️⃣5️⃣ Check Missing Values

```python
combined_df.isnull().sum()
```

Purpose:
- Identify missing/null values

---

## 1️⃣6️⃣ Fill Missing Values

Used:

```python
combined_df.fillna("Unknown", inplace=True)
```

Purpose:
- Replace missing values with `"Unknown"`

---

## 1️⃣7️⃣ Drop Remaining Null Values

Used:

```python
combined_df.dropna(inplace=True)
```

Purpose:
- Remove rows still containing null values

---

## 1️⃣8️⃣ Select Important Columns

Selected useful columns:

```python
["title", "rating", "final_price"]
```

Purpose:
- Focus on required data only

---

## 1️⃣9️⃣ Filter High Rated Products

Filtered products having rating greater than 4.

### Operation

```python
combined_df[combined_df["rating"] > 4]
```

Purpose:
- Analyze highly rated products

---

## 2️⃣0️⃣ Remove Duplicate Records

Used:

```python
combined_df.drop_duplicates(inplace=True)
```

Purpose:
- Remove repeated rows

---

# ➕ Feature Engineering

## 2️⃣1️⃣ Create Quantity Column

Added a new column:

```python
combined_df["quantity"] = 2
```

Purpose:
- Assign fixed quantity value

---

## 2️⃣2️⃣ Create Total Amount Column

Created a derived column:

```python
total_amount = final_price * quantity
```

### Operation

```python
combined_df["total_amount"] = (
    combined_df["final_price"] *
    combined_df["quantity"]
)
```

Purpose:
- Calculate total product amount

---

# 💾 Save Final Cleaned Dataset

Saved cleaned dataset as:

```text
cleaned_shopping_dataset.csv
```

---

# 📁 Output Files Generated

| File Name | Description |
|---|---|
| combine_shopping_dataset.csv | Combined raw dataset |
| cleaned_shopping_dataset.csv | Final cleaned dataset |
| Shopping_Dataset_Analysis.ipynb | Jupyter Notebook |

---

# ✅ Final Outcome

Successfully performed:

- Data extraction
- CSV loading
- Dataset merging
- Data exploration
- Missing value handling
- Duplicate removal
- Filtering operations
- Feature engineering
- Cleaned dataset generation

---

# 📚 Learning Outcomes

Through this project, the following concepts were learned:

- Python basics
- Pandas DataFrame operations
- File handling
- Data cleaning techniques
- Data exploration methods
- CSV operations
- Feature engineering basics

---

# 🔗 Dataset Reference

Kaggle Shopping Dataset:  
https://www.kaggle.com/datasets/anvitkumar/shopping-dataset

---

# 👨‍💻 Author

Pranjal Upadhyay

B.Tech CSE (AI & Data Science)  
Purnima University, Jaipur

```
