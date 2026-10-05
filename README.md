# 🏠 Airbnb Open Data Analysis

An exploratory data analysis (EDA) of Airbnb listings in New York City using Python. The project walks through loading, cleaning, and visualizing the data to understand how listings are distributed across boroughs and room types, and how prices vary between them.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Tools & Libraries](#-tools--libraries)
- [Project Workflow](#-project-workflow)
- [Data Cleaning Steps](#-data-cleaning-steps)
- [Visualizations](#-visualizations)
- [How to Run](#-how-to-run)
- [Repository Structure](#-repository-structure)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 📖 Project Overview

The goal of this project is to explore the Airbnb Open Data and answer questions such as:

- Which boroughs have the most listings?
- Which room types are most common?
- What are the average and median prices?
- How does price vary by room type and by borough?
- Is there any relationship between the number of reviews and price?

---

## 📂 Dataset

- **File:** `Airbnb_Open_Data.xlsx`
- **Size:** ~102,600 rows × 26 columns (before cleaning)
- **Scope:** Airbnb listings in New York City

| Category | Columns |
|----------|---------|
| Listing info | `id`, `NAME`, `room type`, `Construction year`, `house_rules`, `license` |
| Host info | `host id`, `host name`, `host_identity_verified`, `calculated host listings count` |
| Location | `neighbourhood group`, `neighbourhood`, `lat`, `long`, `country`, `country code` |
| Pricing & booking | `price`, `service fee`, `minimum nights`, `instant_bookable`, `cancellation_policy`, `availability 365` |
| Reviews | `number of reviews`, `last review`, `reviews per month`, `review rate number` |

---

## 🛠 Tools & Libraries

- **Python 3**
- **Pandas** – data loading and cleaning
- **NumPy** – numerical operations
- **Matplotlib** – plotting
- **Seaborn** – statistical visualizations
- **Jupyter Notebook / Google Colab**

---

## 🔄 Project Workflow

1. **Import libraries**
2. **Load the data** from the Excel file
3. **Data overview** – shape, columns, `info()`, and summary statistics
4. **Data cleaning** – duplicates, missing values, typos, invalid values
5. **Analysis** – listing counts, price statistics
6. **Visualization** – individual charts and a combined dashboard

---

## 🧹 Data Cleaning Steps

- Removed **duplicate rows**
- Filled missing **categorical** values with `'Unknown'`
- Filled missing `number of reviews` and `reviews per month` with `0`
- Dropped rows with a missing **price** (key variable for analysis)
- Fixed typos in `neighbourhood group` (`manhatan` → `Manhattan`, `brookln` → `Brooklyn`)
- Treated invalid values as missing and imputed with the **median**:
  - `minimum nights` outside 1–365
  - `availability 365` outside 0–365
- Imputed `Construction year`, `service fee`, and `calculated host listings count` with the **median**
- Converted `last review` to a datetime type
- Dropped rows with missing `lat` / `long`
- Dropped the `license` column (almost entirely empty)

---

## 📊 Visualizations

The notebook produces the following charts, which are also combined into a single 2×2 **Airbnb Data Dashboard**:

1. **Listings by Borough** – bar chart
2. **Listings by Room Type** – bar chart
3. **Price Distribution by Room Type** – box plot
4. **Price Distribution by Neighbourhood Group** – box plot
5. **Price vs. Number of Reviews** – scatter plot

> 💡 *Tip: Save your chart images into an `images/` folder and embed them here, e.g.* `![Dashboard](images/dashboard.png)`

---

## ▶️ How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Shiva2202/Airbnb-Data-Analysis.git
   cd Airbnb-Data-Analysis
   ```

2. **Install the dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl jupyter
   ```

3. **Launch the notebook**
   ```bash
   jupyter notebook Airbnb_Data_Analysis.ipynb
   ```

4. **Update the file path** in the data-loading cell to point to your local copy of the dataset:
   ```python
   file_path = 'Airbnb_Open_Data.xlsx'
   data = pd.read_excel(file_path)
   ```

> The notebook was originally written in **Google Colab** (`/content/Airbnb_Open_Data.xlsx`), so the path needs to be changed when running locally.

---

## 📁 Repository Structure

```
├── Airbnb_Data_Analysis.ipynb   # Main analysis notebook
├── Airbnb_Open_Data.xlsx        # Dataset
├── images/                      # (optional) saved charts
└── README.md                    # Project documentation
```

---

## 🚀 Future Improvements

- Handle **price outliers** (e.g., using IQR) for clearer visuals
- Add a **map** of listings using latitude/longitude
- Analyze **host behavior** (verified hosts, multi-listing hosts)
- Study the effect of **cancellation policy** and **instant booking** on price
- Build an interactive dashboard with **Plotly** or **Streamlit**
- Add a **price prediction** model

---

## 👤 Author

**Borath Shiva Kumar**

- GitHub: [@Shiva2202](https://github.com/Shiva2202)
- LinkedIn: [Shiva Kumar Borath](https://www.linkedin.com/in/shiva-kumar-borath)

---

⭐ If you found this project useful, consider giving it a star!
