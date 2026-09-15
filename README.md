## EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)
### Aaron Siegfreid R. Jugo
### 2ECE-A
### 9/15  /2026 

### Objectives:
At the end of this laboratory activity, the student should be able to:
1. Load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. Extract a well-defined subset of data without changing the source data

The student must use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Notebook-
book and import Pandas as pd. The dataset contains the Model column together with the vehicle
variables used in the original experiment.
- Load the CSV file into a DataFrame named cars.
- Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any
requested table or answer.
- Do not modify values in cars; create a new DataFrame or Series for each requested subset.
- Preserve the row order of the source dataset unless stated otherwise.
- Display every requested result in an executed notebook cell.
----------------------------------------------------------------------------------------------------
### A. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations.
a. Display the shape and complete list of column names of cars.
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order


Code:

```
import pandas as pd 

cars = pd.read_csv("cars.csv") 
cars
```

```
print("Shape of cars: ", cars.shape)
```
```
c_col = cars.columns

print("\nColumn List of Cars: ", list(c_col))
```
```
cars_6_to_10 = cars[5:10]

print("\nRows 6 to 10:")
cars_6_to_10
```
```
print("Rows 6 to 10 with Specified Columns:\n")
display(cars_6_to_10.loc[5:10,['Model', 'mpg', 'cyl', 'hp', 'gear']])
```
Output:
The output aligned with the required result:

- Displayed cars.csv


<img width="576" height="387" alt="image" src="https://github.com/user-attachments/assets/8be4dbf6-9b75-4a6c-9034-a462e63d4b24" />


- Displayed the shape of cars, a column list of cars, and Rows 6 to 10:
```
Shape of cars:  (32, 12)

Column List of Cars:  ['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']

Rows 6 to 10:
```
<img width="512" height="172" alt="image" src="https://github.com/user-attachments/assets/c0daa9f8-f5b3-4a3b-a377-20bf8b3b5b38" />


- Printed rows with specified columns.
```
Rows 6 to 10 with Specified Columns:
```
<img width="253" height="181" alt="image" src="https://github.com/user-attachments/assets/f0820ebc-cada-4cd1-924a-0d5152277d3f" />


---------------------------------------------------------------------------------------
### B. MODEL LOOKUP
Use Boolean indexing on the Model column to answer both requests.
a. Display the complete row for Toyota Corolla.
b. For Pontiac Firebird, display only Model, mpg, hp, and wt.
Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

