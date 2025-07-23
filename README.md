# Orphaned_Wells_USA
An interactive data analysis and geospatial visualization project exploring the distribution and status of orphaned wells across the United States using Python and Plotly.

# What are Orphaned Wells? 
Orphaned wells are oil and gas wells that have been abandoned by their operators without proper closure or plugging, and for which no legally responsible party can be found. These wells were typically drilled decades ago, and over time, the original companies may have gone bankrupt, changed ownership, or ceased operations without fulfilling regulatory obligations. It is a serious concern because, environmental hazards, public safety risks and financial burden. Analyzing orphaned wells help to see which state are at higher risk and also raise public awareness about long-term fossil infrastructure impacts.


# USA Orphaned Wells Data Analysis & Visualization Project

This project uses real environmental data from the **U.S. Environmental Protection Agency (EPA)** to explore and visualize orphaned and abandoned oil and gas wells across the United States. The goal is to clean, analyze, and visualize well location data using **Python**, **pandas**, and **Plotly**, while uncovering potential environmental insights.

---
## Dataset
- **Source**: U.S. Environmental Protection Agency (EPA)
- **File**: `US_orphaned_wells.csv` (original), `cleaned_orphaned_wells.csv` (cleaned)
- **Size**: ~100,000 records
- **Fields**:
  - `State`, `County`
  - `Status`: Well status (e.g., Plugged, Orphaned, Abandoned)
  - `Latitude`, `Longitude`
  - (Optional: `spud_date`, `plug_date` if available)
---
## Project Features

### Data Cleaning
- Simplified and standardized `Status` values (e.g., `PA`, `OR` → `PLUGGED`, `ORPHANED`)
- Removed missing or invalid coordinates
- Reformatted and cleaned column names

### Exploratory Data Analysis (EDA)
- Distribution of well status types
- Total wells per state
- Frequency of well types and statuses
- Missing value and outlier checks

### Geospatial Mapping
- Interactive map of all well locations using `latitude` and `longitude`
- Colored by well status 
- USA scope map using Plotly Express

### Visualizations
- Bar chart: Total wells by state
- Pie chart: Distribution of well statuses
- Interactive geographic map

## Tools & Libraries
- Python 3.x
- pandas
- plotly (Express & Graph Objects)
- matplotlib
- Jupyter Notebook
---
# Data Cleaning Process
Data Cleaning Process:
The raw dataset from the U.S. Environmental Protection Agency contained over 100,000 oil and gas well records with inconsistent formatting, missing values, and a large number of categorical codes — especially in the Status column.

Key Cleaning Steps:
1.Standardized Column Names
2.Converted all column names to lowercase
3.Replaced spaces with underscores for consistency (e.g., Plug Date → plug_date)
4.Handled Missing Coordinates
5.Dropped records with missing latitude or longitude, which are required for mapping
6.Standardized Text Fields
7.Converted values in status, state, and county to uppercase and stripped whitespace
Example: " Plugged " → "PLUGGED"

Grouped Inconsistent Status Values
The raw Status column included over 40+ different labels and abbreviations such as: "PA", "P&A", "PR", "Abandoned, Unknown Location", "Orphaned Well", "WO", "TA" etc.

These were grouped into 9 main categories to simplify analysis:

Original Values	Grouped As
PA, P&A, XX, etc.	-- PLUGGED
OR, Orphaned, Forfeited, etc.	-- ORPHANED
AB, Abandoned Well, etc. --	ABANDONED
TA, Idle, SI, etc. --	TEMP_ABANDONED
Active, AL, HP, etc.-- ACTIVE
WO --	WORKOVER
Canceled, DA, DM --	CANCELLED
Environmental Reclamation	-- RECLAMATION
Unknown, UN, etc. -- UNKNOWN

The main column selected for this study will be State, County, Long, Lat , Status

Saved Cleaned Dataset

The cleaned dataset was exported as cleaned_orphaned_wells.csv and used for all analysis and visualizations.


