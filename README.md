# Titanic Dataset - Data Cleaning Project

## Overview

This project demonstrates a basic data-cleaning workflow using the
publicly available Titanic passenger dataset.

The objective is to identify and handle missing values, check data
types, check duplicate records, validate the cleaned dataset, and
document the assumptions made during the cleaning process.

## Objectives

- Inspect the raw dataset
- Identify missing values
- Handle missing values
- Check for duplicate records
- Handle appropriate data types
- Validate the cleaned dataset
- Document cleaning assumptions
- Export the cleaned dataset

## Dataset

The dataset contains information about passengers aboard the Titanic.

Important columns include:

- `PassengerId` - Unique passenger identifier
- `Survived` - Whether the passenger survived
- `Pclass` - Passenger class
- `Name` - Passenger name
- `Sex` - Passenger sex
- `Age` - Passenger age
- `SibSp` - Number of siblings/spouses aboard
- `Parch` - Number of parents/children aboard
- `Ticket` - Ticket number
- `Fare` - Passenger fare
- `Cabin` - Cabin information
- `Embarked` - Port of embarkation

## Data Cleaning Process

### 1. Missing Value Analysis

Missing values were identified and counted for each column.

### 2. Cabin

Missing values in the `Cabin` column were replaced with `"Unknown"`.

This preserves the rows while clearly indicating that cabin information
was unavailable.

### 3. Age

Missing values in the `Age` column were replaced with the median age.

The median was selected because Age is numerical and the median is less
affected by extreme values than the mean.

### 4. Embarked

Missing values in the `Embarked` column were replaced with the most
frequently occurring value (mode).

Only a small number of observations had missing values.

### 5. Duplicate Records

The dataset was checked for duplicate rows.

No duplicate rows were found.

### 6. Data Types

The `Sex`, `Cabin`, and `Embarked` columns were converted to the
`category` data type because they represent categorical information.

### 7. Validation

The cleaned dataset was checked for:

- Missing values
- Duplicate records
- Dataset dimensions
- Data types

### 8. Export

The cleaned dataset was saved as:

`data/titanic_cleaned.csv`

## Assumptions

1. Missing `Cabin` values were replaced with `"Unknown"` because the
   original cabin information was unavailable.

2. `"Unknown"` does not imply that the passenger did not have a cabin.
   It only indicates that the information was not available in the dataset.

3. Missing `Age` values were replaced with the median age because Age is
   numerical and the median is relatively robust to extreme values.

4. Missing `Embarked` values were replaced with the mode because only a
   small number of values were missing.

5. Duplicate rows were checked, and no duplicate rows were found.

6. No rows were removed during the cleaning process. Missing information
   was handled through replacement wherever possible.

## Project Structure

```text
titanic-data-cleaning/
│
├── data/
│   ├── titanic.csv
│   └── titanic_cleaned.csv
│
├── notebooks/
│   └── data_cleaning.ipynb
│
├── src/
│
├── .gitignore
├── requirements.txt
└── README.md