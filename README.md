# Student Risk Analysis: Exploratory Data Analysis & Feature Engineering

> **Short Description**
> This project conducts an end-to-end Exploratory Data Analysis (EDA) and feature engineering pipeline on college student management data. It focuses on identifying academic risk factors by optimizing memory, encoding categorical variables, engineering engagement metrics, and visualizing correlations to prepare the dataset for predictive machine learning models.

## 🎯 Project Objective
To transform raw, structural academic data into a fully optimized, machine-readable dataset. This analysis investigates the underlying behavioral factors that contribute to a student's academic standing and builds the foundational data pipeline required for predictive "at-risk" classification models.

## 🗄️ Dataset Overview
The dataset contains organizational records for college students, capturing a mix of demographic, academic, and behavioral metrics, including:
*   **Numerical Features:** `GPA`, `attendance_rate`, `lms_logins_past_month`, `assignment_submission_rate`
*   **Categorical Features:** `major`, `gender`, `enrollment_status`
*   **Target Variable:** `risk_level` (Low, Medium, High)

## 🛠️ Key Analytical Pipeline

### 1. Data Integrity & Optimization
*   Verified structural integrity (zero missing values, handled duplicates).
*   Optimized system memory footprint by downcasting numerical types (e.g., converting standard 64-bit integers to `int8` and continuous metrics to `float32`).
*   Handled severe outliers in digital engagement metrics using percentile capping.

### 2. Feature Engineering
*   **Composite Metrics:** Engineered a `total_engagement` score by aggregating attendance, assignment submissions, and video completion rates.
*   **Behavioral Ratios:** Calculated `actions_per_login` to measure the depth of engagement per session.
*   **Segmentation:** Applied categorical binning to convert continuous age data into discrete `age_group` tiers.

### 3. Categorical Translation for ML
*   **Ordinal Encoding:** Mapped hierarchical text variables (`risk_level`) into numerical weights.
*   **One-Hot Encoding:** Converted nominal variables (e.g., `major`) into binary matrices to prevent algorithms from inferring false mathematical ranks.

### 4. Statistical Visualization
*   Conducted univariate and bivariate analysis to examine data distributions.
*   Generated a comprehensive correlation matrix to mathematically validate relationships between independent variables and the target GPA.

## 📊 Key Insights & Findings
*   **Variable Independence:** The correlation heatmap revealed that individual behavioral metrics (such as `lms_logins_past_month` and `forum_participation_count`) exhibit very weak direct mathematical correlations (near `0.00`) with overall `GPA`. This indicates that academic success in this dataset is highly multi-dimensional and not driven by a single isolated action.
*   **Demographic Consistency:** Violin plot distributions confirmed a consistent GPA variance across all recorded genders, indicating no underlying systemic bias or statistical skew in academic performance based on demographic lines.

## 🖼️ Visualizations

*(Note: Ensure `heatmap.png` and `violin_plot.png` are uploaded to the root of this repository to render below)*

### Correlation Matrix
![Correlation Heatmap](heatmap.png)

### GPA Distribution by Gender
![Violin Plot](violin_plot.png)

## 💻 Tech Stack
*   **Pandas:** Data manipulation, cleaning, categorical encoding, and memory optimization.
*   **NumPy:** Mathematical transformations, clipping outliers, and logical masking.
*   **Matplotlib & Seaborn:** Statistical data visualization and color-mapped correlation plotting.
