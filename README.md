# 🚗 Road Accident Analysis in France — 2024

## 📊 Power BI Data Analytics Project

This project analyzes **road traffic accidents in France in 2024** using official data from the **French Road Safety Observatory (ONISR)**.

The objective is to clean, transform, analyze, and visualize road accident data using **Power BI**, with a focus on accident characteristics, road conditions, vehicles, road users, severity, and key trends.

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Analyze the number and distribution of road accidents in 2024.
* Identify the main characteristics of road accidents.
* Analyze accident locations and road conditions.
* Study the characteristics of vehicles involved in accidents.
* Analyze road users by age, sex, severity, and safety equipment.
* Identify important patterns and trends.
* Build an interactive Power BI dashboard.
* Present key insights in a clear and professional way.

---

## 📁 Dataset

The project uses the official **BAAC (Bulletins d'Analyse des Accidents Corporels)** database.

The 2024 dataset is divided into four main tables:

| Table                         | Description                                |
| ----------------------------- | ------------------------------------------ |
| `caracteristiques_2024_clean` | General characteristics of accidents       |
| `lieux_2024_clean`            | Accident location and road characteristics |
| `vehicules_2024_clean`        | Vehicles involved in accidents             |
| `usagers_2024_clean`          | Road users involved in accidents           |

### Main Variables

Some of the main variables used include:

* `Num_Acc` — Accident identifier
* `id_usager` — User identifier
* `id_vehicule` — Vehicle identifier
* `grav` — User severity
* `sexe` — Sex
* `an_nais` — Year of birth
* `trajet` — Trip purpose
* `secu1`, `secu2`, `secu3` — Safety equipment
* `catv` — Vehicle category
* `manv` — Vehicle maneuver
* `obs` — Obstacle
* `choc` — Collision type
* `situ` — Accident location situation
* `surf` — Road surface
* `infra` — Infrastructure
* `vma` — Speed limit

---

## 🧹 Data Preparation

The raw datasets were imported into **Power Query** and cleaned before analysis.

The main preparation steps included:

1. Importing the 2024 BAAC datasets.
2. Promoting the first row to column headers.
3. Checking column names and data types.
4. Converting numeric variables to appropriate numerical types.
5. Converting text variables to text format.
6. Identifying missing values.
7. Checking categorical variables and their distributions.
8. Creating calculated columns where necessary.
9. Creating an `Age` column from the year of birth.
10. Removing invalid age values from the analysis.
11. Preparing the cleaned tables for Power BI analysis.

### Missing Values

Missing values were identified in several variables.

For example, `an_nais` contained missing values, so the age calculation was designed to ignore invalid or missing birth years.

---

## 🧮 DAX Measures

Several DAX measures were created to ensure that the dashboard counts unique entities correctly.

### Total Accidents

```DAX
Total Accidents =
DISTINCTCOUNT(caracteristiques_2024_clean[Num_Acc])
```

### Total Users

```DAX
Total Users =
DISTINCTCOUNT(usagers_2024_clean[id_usager])
```

### Total Vehicles

```DAX
Total Vehicles =
DISTINCTCOUNT(vehicules_2024_clean[id_vehicule])
```

### Fatal Users

```DAX
Fatal Users =
CALCULATE(
    DISTINCTCOUNT(usagers_2024_clean[id_usager]),
    usagers_2024_clean[grav] = 2
)
```

Using `DISTINCTCOUNT` is important because the same accident, user, or vehicle identifier can appear in multiple records.

---

## 📊 Power BI Dashboard

The dashboard is organized into **four pages**.

### Page 1 — Overview

The first page provides a general overview of road accidents in 2024.

It includes:

* Total accidents
* Accident trends
* Main accident characteristics
* General accident distribution
* Interactive filtering

---

### Page 2 — Road Analysis

This page focuses on the characteristics of accident locations and roads.

The analysis includes:

* Road category
* Road characteristics
* Road surface
* Infrastructure
* Road conditions
* Accident location information

---

### Page 3 — Users & Vehicles

This page analyzes the people and vehicles involved in road accidents.

Main visuals include:

* Total Users
* Users by Severity
* Users by Sex
* Severity Distribution by Sex
* Users by Age
* Users by Safety Equipment
* Accidents by Vehicle Category
* Accidents by Maneuver
* Accidents by Obstacle

---

### Page 4 — Key Insights & Analysis

The final page summarizes the most important findings.

It includes four main KPI cards:

* **Total Accidents**
* **Total Users**
* **Total Vehicles**
* **Fatal Users**

Additional visuals include:

* Accidents by Day of Week
* Accidents by Location Type
* Accidents by Vehicle Category
* User Severity Distribution
* Key Findings

---

## 🎛️ Interactive Features

The dashboard includes interactive slicers that allow users to filter the analysis by:

* **Month**
* **Day of Week**
* **Light Condition**

The slicers are synchronized across the dashboard pages so that users can explore the data interactively.

A **Page Navigator** was also added to make navigation between the four dashboard pages easier.

---

## 🔎 Key Findings

The analysis highlights several important patterns in the 2024 road accident data:

* **Friday recorded the highest number of accidents**, while Sunday recorded the lowest.
* **Most accidents occurred on the roadway.**
* **Severity category 1 was the largest user group**, accounting for approximately 42.27% of users.
* **Severity category 4 represented approximately 39.71% of users**, making it the second-largest category.
* **Fatal users represented approximately 2.7% of all users.**

> **Note:** Severity and categorical variables use official BAAC coding. The original codes are preserved in the dataset to maintain data integrity.

---

## 🛠️ Tools & Technologies

The project was developed using:

* **Power BI Desktop**
* **Power Query**
* **DAX**
* **Microsoft Excel / CSV**
* **GitHub**

### Skills Demonstrated

This project demonstrates practical skills in:

* Data cleaning
* Data transformation
* Exploratory data analysis
* Data visualization
* Power Query
* DAX
* KPI development
* Dashboard design
* Data storytelling
* Interactive reporting

---

## 📂 Project Structure

A recommended GitHub repository structure is:

```text
road-accident-analysis-france-2024/
│
├── README.md
│
├── data/
│   ├── caracteristiques-2024.csv
│   ├── lieux-2024.csv
│   ├── vehicules-2024.csv
│   └── usagers-2024.csv
│
├── powerbi/
│   └── road-accident-analysis-2024.pbix
│
├── screenshots/
│   ├── page-1-overview.png
│   ├── page-2-road-analysis.png
│   ├── page-3-users-vehicles.png
│   └── page-4-key-insights.png
│
└── documentation/
    └── data-dictionary.md
```

---

## 🖼️ Dashboard Preview

Add your Power BI screenshots to the `screenshots/` folder and display them here.

### Overview

```text
screenshots/page-1-overview.png
```

### Road Analysis

```text
screenshots/page-2-road-analysis.png
```

### Users & Vehicles

```text
screenshots/page-3-users-vehicles.png
```

### Key Insights

```text
screenshots/page-4-key-insights.png
```

---

## 📚 Data Source

The project uses official French road accident data from the **Observatoire National Interministériel de la Sécurité Routière (ONISR)**.

Official dataset:

[BAAC Road Accident Databases — 2005–2024](https://www.data.gouv.fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2024)

Official ONISR:

https://www.onisr.securite-routiere.gouv.fr/

---

## ⚠️ Data & Methodology Notes

* The project analyzes **2024 accident data**.
* The original BAAC identifiers and categorical codes are preserved.
* Missing values are not automatically interpreted as zero.
* Invalid birth years are excluded from age calculations.
* Unique accidents, users, and vehicles are calculated using `DISTINCTCOUNT`.
* Categorical codes should be interpreted using the official BAAC coding documentation.
* Dashboard results depend on the cleaned dataset and the transformations applied in Power Query.

---

## 🚀 Future Improvements

Possible future developments include:

* Adding multiple years of data (2019–2024).
* Building a year-over-year accident trend.
* Adding geographic analysis by region or department.
* Creating a map of accident locations.
* Developing predictive models for accident severity.
* Adding statistical analysis using Python.
* Integrating machine learning models.
* Creating a more advanced Power BI data model.
* Adding automated data refresh.
* Creating a dedicated data dictionary.

---

## 👨‍💻 Author

**Omar**

Applied Economics & Data Science

This project was developed as part of a personal **Data Analytics / Power BI portfolio** to demonstrate practical skills in data cleaning, analysis, visualization, and data storytelling.

---

## ⭐ Project Highlights

**Dataset:** BAAC 2024
**Domain:** Road Safety / Transportation
**Tool:** Power BI
**Language:** English
**Dashboard Pages:** 4
**Main Techniques:** Power Query + DAX + Data Visualization

---

## 📌 License & Data Usage

The data used in this project originates from publicly available French government road safety datasets.

Please refer to the original data source for the applicable terms of reuse and licensing.

---

**If you find this project useful, feel free to ⭐ the repository.**
