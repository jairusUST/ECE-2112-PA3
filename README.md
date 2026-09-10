# ECE-2112-PA-3

Created by: Jairus Gabriel Ramos | 2ECE-D

# EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)

This repository contains my Programming Assignment 3 for our Advanced Computer Programming and Algorithms course. It covers three data analysis problems using Pandas.

## Objective

The objective of this activity is to practice loading data using Pandas, using indexing, Boolean conditions, and selecting data from a DataFrame.

## A. Positional and Label-Based Slicing

For the first problem, I loaded the `cars.csv` file using Pandas.

The code used was:

```python
import pandas as pd
cars = pd.read_csv('/content/cars.csv')
```

I displayed the shape and columns of the DataFrame.

I then selected rows 6 to 10 using positional indexing:

```python
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10
```

I selected the required columns:

```python
cars_6_to_10[['Model','mpg','cyl','hp','gear']]
```

## B. Model Lookup

For the second problem, I used Boolean conditions to find specific car models.

For Toyota Corolla:

```python
toyota = cars.loc[cars['Model']=='Toyota Corolla']
toyota
```

For Pontiac Firebird:

```python
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model','mpg','hp','wt']]
pontiac
```

## C. Multi-Model Subsetting

For the third problem, I selected the Datsun 710, Lotus Europa, and Ferrari Dino using Boolean conditions.

```python
selected_cars = cars.loc[
    (cars['Model'] == 'Datsun 710') |
    (cars['Model'] == 'Lotus Europa') |
    (cars['Model'] == 'Ferrari Dino'),
    ['Model','mpg','cyl','hp','gear']
]
selected_cars
```

The resulting DataFrame has a shape of `(3, 5)`.
