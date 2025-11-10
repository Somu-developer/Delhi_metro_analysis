# Delhi_metro_analysis
Analysis on delhi metro dataset 

# 🧭 Delhi Metro Trips Analysis

This repository contains an exploratory data analysis (EDA) of a **Delhi Metro trip-level dataset** (`delhi_metro_updated.csv`).  
The goal is to understand trip patterns, station usage, ticket types, and time trends (trips per month), using Python in a Jupyter Notebook.

> **Note:** This project does **not** include line-level or phase-level analysis because the dataset does not contain columns like `line`, `corridor`, or `phase`.

## 📦 Repository Structure

- Delhi_Metro_Dataset.ipynb # Jupyter notebook with step-by-step analysis
- README.md # Project documentation
- delhi_metro_by_ticket_type (Saved File)
- delhi_metro_cleaned(Saved File)
- delhi_metro_updated.csv # Source data (https://www.kaggle.com/datasets/nikhilkumar766/delhi-metro-dataset)

## 🛠️ What the Notebook Does

1. **Load & Standardize Columns**
   - Renames columns to lowercase, snake_case (e.g. `From Station` → `from_station`)
   - Detects key columns if present:
     - `date`
     - `from_station`
     - `to_station`
     - `ticket_type`
     - `distance_km`
     - `fare`
     - `passengers`

2. **Basic Health Check**
   - Displays missing values per column  
   - In your data:
     - `remarks`: ~17.5% missing (okay, descriptive)
     - `passengers`: ~1% missing
     - `ticket_type`: ~1% missing
     - others: 0% missing → ✅ clean dataset

3. **Data Cleaning**
   - Converts numeric-looking columns (fare, distance_km, passengers) to numeric types  
   - Parses the `date` column into proper datetime format  
   - Drops rows with invalid dates for time-based analysis

4. **Exploratory Analysis**
   - Visualizes numeric distributions (fare, distance, passengers)
   - Displays top origin and destination stations
   - Shows ticket-type breakdown

5. **Comparisons**
   - Groups data by `ticket_type` to calculate:
     - total trips
     - mean/median fare
     - mean/median distance
     - total passengers

6. **Time-Based Analysis**
   - Calculates and visualizes **trips per month**
   - Excludes invalid/missing dates to avoid NaN months
   - Helps reveal ridership trends over time

---

## ▶️ How to Run

1. **Clone the Repository**

git clone https://github.com/<your-username>/Delhi_metro_analysis.git
cd Delhi_metro_analysis

2. **Install Required Libraries**

pip install pandas numpy matplotlib seaborn jupyter

3. **Open the Notebook**

jupyter notebook Delhi_Metro_Dataset.ipynb

4. **Run All Cells**

The notebook will load and clean the dataset
Generate summary tables and charts automatically

5. **Key Insights You Can Derive**

Which ticket types are used most frequently
Which stations appear most as origins and destinations
How fare changes with distance (scatterplot)
How trips vary over months (time trend)

6. **Dataset Notes**

remarks has missing values (non-critical text field)
No line or phase columns, so metro corridor-level analysis isn’t included
Time-based analysis ignores invalid date rows to avoid NaN grouping

7. **Tech Stack**

Python 3.x
pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook

✅ **Future Improvements**

Add new datasets with line or phase info for deeper insights
Build an interactive Streamlit or Dash dashboard
Combine with holiday or weather data for seasonal trends
