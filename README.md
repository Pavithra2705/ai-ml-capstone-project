#  README — Part 1

# **Project Title**

## Applied AI & ML Essentials — Capstone Project

### Part 1: Data Cleaning and Exploratory Data Analysis

---

# **Dataset Used**

I used the **UCI Bike Sharing dataset (`day.csv`)**.

This dataset contains daily bike rental data. Each row represents one full day and includes features like temperature, humidity, windspeed, season, weather situation, and total bike rentals.

### **The main target column is:**

- **`cnt`** → Total bike rentals per day

---

# **What I Did in This Project**

## **1. Loading the Dataset**

I loaded the dataset using **`read_csv()`** and checked the first few rows to understand the structure.

I also checked the data types and shape of the dataset.

---

## **2. Missing Value Analysis**

I checked missing values using **`isnull().sum()`** and calculated the percentage of missing data.

For missing values, I used the **median** for numeric columns where missing values were less than **20%**.

I used median instead of mean because the data has extreme values, and median gives a more stable result.

I verified again using **`isnull().sum()`** to confirm no missing values remained.

---

## **3. Duplicate Values**

I checked duplicate rows using **`duplicated().sum()`** and removed them using **`drop_duplicates()`**.

---

## **4. Data Type Correction**

- **`dteday`** → converted to datetime format
- **`season`**, **`month`**, **`weekday`**, **`holiday`**, **`workingday`**, **`weather situation`** → converted to category type

---

## **5. Memory Usage Check**

I compared memory usage before and after changing data types.

This helps reduce memory usage and improves performance.

---

## **6. Descriptive Statistics and Skewness**

I used **`describe()`** to understand the dataset.

I calculated skewness for numeric columns.

The most skewed columns were identified.

These columns are positively skewed, meaning most values are small but a few values are very large.

---

## **7. Outlier Detection (IQR Method)**

I used the **IQR method** on:

- **`temp`**
- **`cnt`**

I did not remove outliers because they may represent real-life situations like holidays or weather changes.

---

## **8. Visualizations**

I created **5 required plots:**

- **Line plot** → bike demand over time
- **Bar plot** → average bike rentals across seasons
- **Histogram** → distribution of data
- **Scatter plot** → temperature vs bike demand
- **Box plot** → weather vs bike rentals

### **Scatter Plot Insight**

Bike rentals increase when temperature increases.

### **Box Plot Insight**

Bike rentals change across different weather conditions.

---

## **9. Correlation Analysis**

I used a **correlation heat map** to study relationships between numeric columns.

Some variables move together, while others do not.

A strong correlation does not always mean one variable causes the other.

---

## **10. Pearson vs Spearman Comparison**

I compared **Pearson** and **Spearman** correlation values.

Then I found the **top 3 column pairs** with the largest difference.

These pairs show:

- The relationship is not fully straight (non-linear)
- But still follows a clear pattern

For feature selection later, I will consider both, but give more importance to **Spearman** when needed.

---

## **11. GroupBy Analysis**

I grouped data by **season** and calculated:

- Mean
- Standard deviation
- Count

From this, I found:

- Season with highest average bike demand
- Season with highest variation

### **Mean Ratio**

I compared:

- Highest mean season
- Lowest mean season

Then calculated the ratio between them.

This shows how much demand changes across seasons.

---

# **Final Dataset**

After cleaning, I saved the dataset as:

**`cleaned_data.csv`**

This will be used in the next part of the project.

---

# **What I Learned**

I learned that cleaning data is very important before building a machine learning model.

Handling missing values, checking patterns, and creating graphs helps understand the dataset better.

I also learned that season, temperature, and weather strongly affect bike demand.
