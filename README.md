# Share of Students from Abroad Dataset Analysis

This repository contains R code for analyzing the Share of Students from Abroad dataset. The dataset provides information about the inbound mobility rate of students studying abroad by country.

## Dataset Information

The dataset used in this analysis can be found on Kaggle: [Share of Students Studying Abroad Dataset](https://www.kaggle.com/datasets/thedevastator/share-of-students-studying-abroad-by-country).

## Code Explanation

### Data Loading and Exploration
```R
Share.of.Students.from.Abroad <- read.csv("~/Downloads/Kaggle/archive/Share of Students from Abroad.csv")
View(Share.of.Students.from.Abroad)
The code above loads the dataset into R and displays its contents using the read.csv() and View() functions, respectively.

## Package Installation and Loading
install.packages('tidyverse', 'googlesheets4')
install.packages('tidyverse')
library(tidyverse)
These lines install and load the necessary packages for data manipulation and visualization, including 'tidyverse'.

## Data Manipulation
sosa <- Share.of.Students.from.Abroad
sosa2 <- sosa %>% select('Region.or.Country', 'Code', 'Year', 'Inbound.mobility.rate..both.sexes')
The code above creates a new dataframe sosa from the original dataset and selects specific columns for further analysis.

## Data Exploration
table(sosa$Region.or.Country)
sort(table(sosa$Region.or.Country), decreasing = TRUE)
These lines generate a frequency table of countries and sort them in descending order based on the number of observations.

## Filtering Data
sosa1 <- sosa %>%
  group_by(Region.or.Country) %>%
  filter(any( Region.or.Country> 10))
This code filters the dataset to include only rows where the value in the 'Region.or.Country' column is greater than 10 within each group.

## Additional Data Manipulation and Analysis
sosa <- read.csv('/Users/amarewoods/Downloads/Kaggle/archive/Share of Students Studying Abroad.csv')
head(sosa)
This part of the code reads a different version of the dataset and displays its first few rows for comparison.

## Error Correction and Data Cleaning
Sosa1 <- select(sosa, Year >= 2015)
Sosa1 <- drop_na(sosa, Code)
These lines correct errors and clean the data by selecting rows where the 'Year' column is greater than or equal to 2015 and removing rows with missing values in the 'Code' column.
