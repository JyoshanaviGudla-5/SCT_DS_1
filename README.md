# Task 01: World Population Analysis

## 1. Objective
To analyze the global population distribution using World Bank data and visualize the top 10 most populous countries along with the overall distribution of country populations.

## 2. Dataset
- **Source**: World Bank Open Data
- **Indicator**: Population, total (SP.POP.TOTL)
- **File Used**: `Data.csv.xls`
- **Note**: 2023 data has been used for analysis.

## 3. Analysis Performed
1. **Data Cleaning**:
   - Loaded raw Excel file with `skiprows=4` to handle metadata rows
   - Selected data for the year 2023 using column position to avoid `KeyError`
   - Converted `..` missing value markers to `NaN` using `pd.to_numeric(errors='coerce')`
   - Filtered out regional aggregates and income groups like `World`, `High income`, `IBRD`, etc. to keep only sovereign countries

2. **Visualizations**:
   - **Bar Chart**: Top 10 Most Populous Countries in 2023
     - X-axis: Population
     - Y-axis: Country Name
     - Used `seaborn` with `viridis` palette for clarity
   - **Histogram**: Distribution of Country Populations in 2023
     - Used `log_scale=True` on x-axis due to high variance in population data
     - KDE curve added to show distribution shape

## 4. Key Insights
- **India** and **China** are the only countries with populations exceeding 1.4 billion
- **United States** is 3rd with ~340 million, significantly lower than the top two
- The global distribution is heavily right-skewed. Most countries have populations between 1 million and 100 million
- The log-scale histogram shows a peak around 10 million, indicating that is the most common population range for countries

## 5. How to Run
1. Download `Data.csv.xls` from [World Bank Data](https://data.worldbank.org/indicator/SP.POP.TOTL)
2. Place the file in the same directory as the notebook
3. Install required libraries: `pip install pandas matplotlib seaborn numpy openpyxl`
4. Run `Task1_Population_Analysis.ipynb` in Jupyter Notebook or Google Colab

## 6. Skills Demonstrated
- **Data Cleaning**: Handling real-world messy data, missing values, and metadata
- **Pandas**: `read_excel`, `iloc`, `to_numeric`, `dropna`, `str.contains`, `sort_values`
- **Data Visualization**: `Matplotlib`, `Seaborn`, `barplot`, `histplot`, `log_scale`
- **Debugging**: Resolved `KeyError`, `ValueError`, and data type issues
- **Domain Understanding**: Distinguishing between countries and regional aggregates

## 7. Output Files
- `Task1_Population_Analysis.ipynb` - Jupyter notebook with complete code and plots
- `Data.csv.xls` - Raw data file from World Bank
