# Movie Industry Revenue Correlation Analysis (Python)

An Exploratory Data Analysis (EDA) project investigating the underlying factors that drive financial success in the film industry. Utilizing a Kaggle dataset spanning four decades of cinematic data, this project cleans up raw features and tests structural hypotheses by calculating and visualizing statistical correlation coefficients across key movie metrics.

### 🛠️ Tech Stack & Dependencies
* **Language:** Python 3
* **Environment:** Jupyter Notebook (Anaconda Distribution)
* **Core Libraries:**
  * **Data Manipulation:** `pandas`, `numpy`
  * **Data Visualization:** `seaborn`, `matplotlib`

---

### 🗂️ Analysis Pipeline & Key Operations

1. **Data Ingestion & Inspection:** Read in the comprehensive movie industry dataset (~7,600 rows) and evaluated initial metadata, column categories, and missing data characteristics using a programmatic loop `is_null().mean()`.
2. **Data Type Standardization:** Cleaned up visual clutter by stripping floating-point zeros from financial indicators (`budget` and `gross`) and casting them cleanly to integer types.
3. **Feature Correction:** Resolved mismatched release timelines by parsing the string-formatted `released` date string to extract a localized, accurate `year_correct` column.
4. **Categorical Encoding ("Numerization"):** Built a target encoding scheme to map text-based object types (`company`, `genre`, `director`, `country`) into numerical category codes (`cat.codes`), enabling categorical variables to be completely analyzed within statistical correlation algorithms.
5. **Correlation Matrix Comparison:** Generated statistical evaluations across distinct correlation types (including **Pearson**, **Kendall**, and **Spearman** variations) to observe stability across coefficients.
6. **Data Linearization (Unstacking):** Transformed multi-dimensional matrices down to a sorted linear pair architecture (`unstack().sort_values()`) to isolate extreme positive correlation pairs immediately.

---

### 📊 Statistical Findings & Visualizations

* **The Primary Hypothesis:** A Pearson correlation analysis confirmed a strong positive relationship (**0.71**) between a movie's **Budget** and its final **Gross Earnings**.
* **The Secondary Insight:** The data exposed a strong secondary correlation (**0.66**) between the total user **Votes** a film received and its financial yield, demonstrating that high viewer engagement strongly mirrors box-office success.
* **The Counter-Intuitive Finding:** Text-based factors like production **Company** and movie **Genre** demonstrated surprisingly low, negligible correlation weights against final gross revenue, disproving the initial premise that prominent production houses inherently dominate higher revenue metrics regardless of individual film features.

#### Key Visual Highlights Included:
* Customized **Seaborn Regression Plots (`sns.regplot`)** highlighting the trendline mapping out budget versus gross metrics.
* Comprehensive **Seaborn Heatmaps (`sns.heatmap`)** highlighting visual spectrum cues ranging from absolute independent relationships (dark/black zones) to intense correlations (bright/light zones).

---

### 🚀 How to Run the Notebook
1. Clone this repository to your local machine.
2. Download the `movies.csv` dataset file from Kaggle and place it in your local directory.
3. Open Anaconda Navigator, launch Jupyter Notebooks, and open `movie_correlation_project.ipynb`.
4. Run all cells to recreate the cleaning operations, mathematical pairings, and graphical heatmaps.
