# ECE-2112-Programming Assignment 3

**Made by** Ma. Ysabelle T. Laxamana **|** 2ECE-C

This repository contains the Programming Assignment 3: Python Data Analysis (Pandas) for the course ECE2112: Advanced Computer Programming and Algorithms for the school year 2026-2027. This project covers three Python problems pertaining to Module 3: Pandas.

## Objective
The objective of this laboratory activity is to demonstrate proficiency in utilizing the Pandas library to load a CSV dataset into a Data Frame, select rows and columns using positional and label-based indexing, filter data using Boolean conditions, and extract specific subsets of data without altering the original dataset.

## Programming Problems

### A. POSITIONAL AND LABEL-BASED SLICING
Import the provided CSV file into Pandas. Print the Data Frame's shape and full column list. Finally, extract rows 6–10 using `iloc` and specific column labels.

**The following Pandas functions and methods were used in this problem:**

* **`pd.read_csv()`** - used to load the CSV file dataset  into a structured Pandas Data Frame.
* **`.shape`** - used to retrieve the exact dimensions of the Data Frame.
* **`.columns.tolist()`** - used to extract and display the complete list  of column headers as a list.
* **`.iloc`**- used for pure integer-location based indexing to precisely slice rows 6 to 10 from the dataset.
* **Label-based Indexing** - used to extract specific columns by directly calling their string names.

```python
import pandas as pd
cars = pd.read_csv('cars.csv') 

print("Shape of cars:", cars.shape) 
print("Column names:", cars.columns.tolist())

cars_6_to_10 = cars.iloc[5:10] 
cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

### B. MODEL LOOKUP
Use Boolean filtering to extract a specific data record. This retrieves the exact data for Toyota Corolla and Pontiac Firebird. 

**The following Pandas functions and methods were used in this problem:**

* **Boolean Indexing** - used to filter the dataset by applying a strict true false condition to t the 'Model' column.
* **`.loc`** - used to access a group of rows and columns by labels or a Boolean array, allowing for simultaneous row filtering and column extraction.

```python
toyota = cars[cars['Model'] == 'Toyota Corolla']

toyota
```
```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]

pontiac
```
### C. MULTI-MODEL SUBSETTING
Create a customized Data Frame by using multiple Boolean statements to isolate three specific car models. This subset is then filtered down to display only five key performance metrics, ensuring the source data remains completely the same.

**The following Pandas functions and methods were used in this problem:**
* **Boolean Conditions** - used to chain several conditional statements together using the **OR** operator, successfully filtering for three exact vehicle models simultaneously.
* **`.loc`** - used to apply the combined Boolean filter and strictly select the required five columns.

```python
selected_cars = cars.loc[(cars['Model']=='Datsun 710')|(cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]

print("Shape of selected cars:", selected_cars.shape)
selected_cars
```

**Thank you for reading!**

To access the full Python code for Programming Assignment 3, download the file from this link: https://github.com/MaYsabelleLaxamana/ECE-2112-PA-3/blob/main/LAXAMANA_PA3.ipynb. To execute the code, open the file in Jupyter Notebook and run all the cells.

**README file Version History:**

* **September 5, 2026** - Initial README output uploaded.
* **September 11, 2026** - Corrected a minor typographical error in the readme file.
