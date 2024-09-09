# Exploratory-data-analysis

This repository contains a Python script for performing Exploratory Data Analysis (EDA) on a world population dataset using pandas, seaborn, and matplotlib. The goal of this project is to analyze and visualize world population data to extract meaningful insights. The dataset includes information on the population of countries across different continents.

## Dataset

- **File:** world_population_EDA.csv
- **Description:** The dataset includes columns such as country names, population figures for various years, and continent information.

## Key Steps and Analysis

1. **Load and Inspect Data:**
   The script begins by reading the CSV file into a pandas DataFrame. It then displays basic information about the dataset, including data types, null values, and unique values. The `pd.set_option("display.float_format", lambda x: "%.2f" % x)` is used to format the floating-point numbers to two decimal places.

2. **Data Summary:**
   The script provides a summary of the data using `df.info()`, `df.describe()`, and checks for null values with `df.isnull().sum()`. It also counts unique values per column with `df.nunique()`, and identifies the top 10 countries by population for the year 2022 using `df.sort_values("2022 Population", ascending=False).head(10)`.

3. **Population Insights:**
   The script calculates the average population by continent with `df.groupby("Continent")[df.columns[5:12]].mean().sort_values(by='2022 Population', ascending=False)`. It then filters the data for Oceania and visualizes the results using `df2.plot()`. Transposed and reversed visualizations are created to provide a clearer representation of the data. A boxplot is also generated to observe the distribution of population data across continents.

4. **Visualization:**
   - The `df2.plot()` generates a line plot of average population by continent.
   - The transposed DataFrame `df3` is plotted and reversed to show population trends more clearly.
   - Boxplots are created with `df3.boxplot(figsize=(13,5))` to display the distribution of population data for each continent.

5. **Data Types and Filtering:**
   The script also displays the data types of the columns with `df.dtypes` and provides practice with selecting numerical and categorical data types using `df.select_dtypes(include='number')` and `df.select_dtypes(include='object')`.

## Usage

1. Clone this repository:

   ```
   git clone https://github.com/yourusername/your-repo.git
   ```

2. Navigate to the project directory:

   ```
   cd your-repo
   ```

3. Install the required libraries (if not already installed):

   ```
   pip install pandas seaborn matplotlib
   ```

4. Run the script
