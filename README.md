# Supermarket-Sales-Analysis

## Project Description
This project focuses on analyzing supermarket sales data to uncover insights, trends, and patterns. The dataset includes information about sales transactions, customer demographics, product categories, and store locations. The analysis involves data cleaning, feature engineering, and exploratory data analysis (EDA) to support business decision-making.

---

## Dataset Overview
The dataset `Supermarket Sales.csv` contains **1006 rows** and **16 columns**:
- `Invoice ID`, `Branch`, `City indicators` (Yangon, Naypyitaw, Mandalay)
- `Customer type`, `Gender`, `Product line`
- `Unit price`, `Quantity`, `Tax 5%`, `Total`
- `Date`, `Time`, `Payment`, `Rating`

### Key Issues Identified:
- Missing values in `Tax 5%` and `Total`
- Inconsistent data types (e.g., `Unit price` stored as text, Negative data entries in `Quantity`)
- Invalid entries in `Customer type` (e.g., "Memberr")
- Time format inconsistencies
- Presence of outliers in numerical columns

---

## Data Cleaning & Preprocessing Steps
1. **Handling Missing Values**:
   - Recalculated `Tax 5%` using formula: `(Unit price × Quantity) × 0.05`
   - Recalculated `Total` as `(Unit price × Quantity) + Tax 5%`

2. **Data Type Conversions**:
   - Converted `Unit price` to numeric after removing non-numeric characters
   - Converted `Date` to datetime format
   - Standardized `Time` column using regex and datetime conversion

3. **Categorical Data Processing**:
   - Corrected invalid `Customer type` entries (e.g., "Memberr" → "Member")
   - Removed rows with invalid categories
   - Dropped duplicates

4. **Handling Negative Values**:
   - `Quantity` column contained negative values, which were corrected using absolute values to ensure consistency.

5. **Outlier Removal**:
   - Used the Interquartile Range (IQR) method to identify and remove outliers in numerical columns like `Rating`.

---

## Feature Engineering
- **City**: Created from binary columns `Yangon`, `Naypyitaw`, `Mandalay`
- **Time of Day**: Categorized into Morning (5AM-12PM), Afternoon (12PM-5PM), Evening (5PM-9PM), Night (9PM-5AM)
- **Day of Week**: Extracted from `Date` column to identify busy days
- **Weekend Indicator**: Created `Is Weekend?` column to identify weekend sales.
- **Revenue per Item**: Computed as `Total / Quantity` to measure per-unit revenue.

---

## Exploratory Data Analysis (EDA)
- **Boxplots** generated for numerical features to analyze distributions and outliers:
  - Unit price
  - Quantity
  - Tax 5%
  - Total
  - Rating
- **Product Performance**: Identified high-selling and low-performing product lines in different aspect like quantity and revenue.
- **Sales Trends Over Time**: Line charts show revenue variation across different days.
- **Sales Distribution by Time of Day**: Showed which time of day had the most sales.
- **Customer Type Analysis**: Shows which type customers contributes most to total sales
- **Sales by City**: Compared revenue between Yangon, Naypyitaw, and Mandalay using bar plots.
- **Payment Method Distribution**: Countplot showing preferred payment methods.

---

## Key Technologies Used
- **Python Libraries**:
  - Pandas (Data manipulation)
  - Matplotlib/Seaborn (Visualization)
  - Regex (Text cleaning)
- **Jupyter Notebook** for interactive analysis

---

## How to Run
1. Install dependencies:
   ```bash
   pip install pandas matplotlib seaborn
   ```
2. Download `Supermarket Sales.csv`.
3. Run the Jupyter Notebook to execute the analysis and generate visualizations.

---

## Future Work
1. Create interactive dashboards.
2. Add machine learning models for sales prediction.  
