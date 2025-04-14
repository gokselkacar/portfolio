# DataSwift-R

## A comprehensive utility package for efficient data analysis workflows in R

---

## 📊 Overview

DataSwift-R (formerly QuickR) is a powerful R utility package designed to streamline data analysis workflows for researchers, data scientists, and analysts. This package addresses common challenges in data preparation and exploration by providing intuitive, efficient functions for data cleaning, outlier detection, and visualization.

By automating routine tasks in the data analysis pipeline, DataSwift-R allows users to spend less time on data preparation and more time extracting meaningful insights from their data.

---

## ✨ Key Features

- **Standardized Data Structure**
  - Automatic column name standardization
  - Consistent naming conventions across datasets
  - Special character handling

- **Data Quality Management**
  - Robust outlier detection using IQR methodology
  - Detailed outlier summaries and visualization
  - Customizable detection thresholds

- **Comprehensive Analysis Tools**
  - Categorical variable summarization
  - Distribution visualization
  - Rapid statistical summaries

- **Simplified Workflow**
  - Single-line function calls for complex operations
  - Consistent output formats
  - Intuitive parameter naming

---

## 🔧 Core Functions

### Data Preparation

| Function | Description |
|----------|-------------|
| `clean_column_names()` | Standardizes column names by converting to lowercase, replacing spaces with underscores, and removing special characters |
| `detect_outliers()` | Identifies unusual data points in numeric columns using the Interquartile Range (IQR) method |

### Data Analysis

| Function | Description |
|----------|-------------|
| `summarize_categorical()` | Provides comprehensive overview of categorical variables including counts, frequencies, and proportions |
| `quick_plot()` | Generates professional histograms with minimal code using ggplot2 |
| `quick_summary()` | Creates comprehensive statistical summaries for all numeric columns |

---

## 🚀 Getting Started

### Installation

```r
# Install from GitHub
devtools::install_github("yourusername/dataswift-r")

# Load the package
library(dataswift)
```

### Basic Usage

```r
# Clean column names
df <- clean_column_names(your_data)

# Detect outliers
outliers <- detect_outliers(df, threshold = 1.5)

# Summarize categorical variables
cat_summary <- summarize_categorical(df$category_column)

# Create quick visualization
quick_plot(df$numeric_column, "Distribution of Values")

# Get statistical summary
stats <- quick_summary(df)
```

---

## 📈 Function Details

### 1. `clean_column_names()`

Standardizes column names for consistency across datasets:

```r
# Before
data <- data.frame("First Name" = c("John", "Jane"), "Last Name!" = c("Doe", "Smith"))
colnames(data)
# [1] "First Name" "Last Name!"

# After
data <- clean_column_names(data)
colnames(data)
# [1] "first_name" "last_name"
```

### 2. `detect_outliers()`

Identifies potential data anomalies using the IQR method:

```r
# Generate sample data with outliers
set.seed(123)
data <- data.frame(values = c(rnorm(100), 15, -15))

# Detect outliers
outliers <- detect_outliers(data$values)
print(outliers)
# Outliers detected: 2
# Outlier threshold: 1.5 * IQR
# Outlier values: 15, -15
```

### 3. `summarize_categorical()`

Provides comprehensive insights into categorical variables:

```r
# Sample categorical data
categories <- factor(c("A", "B", "A", "C", "B", "A", "D", "A"))

# Get summary
cat_summary <- summarize_categorical(categories)
print(cat_summary)
# Category counts:
# A: 4 (50%)
# B: 2 (25%)
# C: 1 (12.5%)
# D: 1 (12.5%)
# Total categories: 4
```

### 4. `quick_plot()`

Creates clean, professional visualizations with minimal code:

```r
# Generate random data
data <- rnorm(1000)

# Create histogram
quick_plot(data, "Normal Distribution Example")
```

### 5. `quick_summary()`

Generates comprehensive statistical summaries:

```r
# Create sample data frame
df <- data.frame(
  age = rnorm(100, mean = 35, sd = 10),
  income = rnorm(100, mean = 50000, sd = 15000)
)

# Get summary statistics
stats <- quick_summary(df)
print(stats)
```

---

## 💡 Use Cases

### Data Science Workflow

DataSwift-R excels at the exploratory phase of data analysis:

1. Import raw data
2. Clean column names with `clean_column_names()`
3. Check for outliers with `detect_outliers()`
4. Explore categorical variables with `summarize_categorical()`
5. Visualize distributions with `quick_plot()`
6. Get statistical overview with `quick_summary()`

### Academic Research

Streamline data preparation for research projects:

- Standardize datasets from multiple sources
- Quickly identify data collection anomalies
- Generate publication-ready summary statistics
- Create exploratory visualizations

### Business Analytics

Accelerate business intelligence workflows:

- Rapidly assess data quality
- Generate quick insights for stakeholder meetings
- Standardize reporting formats
- Improve analysis consistency across teams

---

## 🔬 Technical Implementation

DataSwift-R follows R package best practices:

- Complete package structure with DESCRIPTION and NAMESPACE files
- Comprehensive documentation with examples for each function
- Extensive test coverage using the testthat framework
- Optimized dependencies (primarily ggplot2 for visualization)
- MIT License for maximum flexibility

---

## 🔮 Future Development

Planned enhancements include:

- Advanced data imputation methods
- Time series analysis utilities
- Interactive visualization options
- Expanded statistical testing functions
- Markdown report generation


---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

*Developed as a personal project to simplify and enhance R-based data analysis workflows.*
