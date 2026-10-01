# 🏅 Olympic Games Data Analysis (1896–2016)

An exploratory data analysis (EDA) of Olympic athletes, built with Python, pandas and Seaborn. The project explores who competes at the Games, how participation has changed over 120 years, and which countries, sports and athletes stand out.

> **Project type:** Beginner-friendly portfolio project
> **Tools:** Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

---

## 📌 Project Overview

The Olympic Games bring together thousands of athletes from over 200 National Olympic Committees (NOCs). This notebook cleans an athlete-level dataset and answers questions such as:

1. What does the data look like, and how clean is it?
2. What does the typical Olympic athlete look like (age, height, weight, sex)?
3. How have participation, athlete age and medals changed over the years?
4. Which countries, athletes and sports dominate?
5. Do physical traits relate to winning medals?

## 📂 Dataset

- **File:** `data/dataset_olympics.csv`
- **Size:** 70,000 rows × 15 columns (383 duplicates removed during cleaning)
- **Granularity:** each row is **one athlete's entry in one event**, so an athlete can appear many times. Most counts in the notebook are *entries*, not unique people.
- **Source:** add your dataset link here (for example, the Kaggle page you downloaded it from)

| Column | Description |
|---|---|
| `ID`, `Name` | Athlete identifier and name |
| `Sex`, `Age`, `Height`, `Weight` | Athlete details (height in cm, weight in kg) |
| `Team`, `NOC` | Team name and 3-letter National Olympic Committee code |
| `Games`, `Year`, `Season`, `City` | Which Games, year, Summer/Winter, and host city |
| `Sport`, `Event` | The sport and the specific event |
| `Medal` | Gold / Silver / Bronze (empty means no medal) |

## 🧹 Data Cleaning

- Removed **383 duplicate rows**.
- Kept missing **Age (~4%)**, **Height (~23%)** and **Weight (~24%)** values as they are instead of filling them in, so averages are not distorted.
- Treated an empty **Medal** value as "no medal" (about 86% of rows), not as bad data.
- Counted team medals **once per country, event and Games** when ranking countries, so a relay team's medal is not counted four times.

## 🔍 Analysis Performed

- **Univariate analysis:** gender, age, height, weight and medal distributions
- **Trends over time:** medals, participants, average age and female participation by year
- **Summer vs Winter:** size and age comparison
- **Countries and athletes:** top medal-winning countries, medal mix, a country-by-year heatmap and top individual medalists
- **Sports:** events per sport, average height by sport, and BMI by sport
- **Physical traits and medals:** height vs weight, correlation heatmap, and medalists vs non-medalists

## 📊 Key Findings

- **The typical athlete** is male in about three quarters of entries, with a median age of **25**, an average height of about **175.5 cm** and an average weight of about **70.9 kg**.
- **Participation grew** from under 100 athletes in 1896 to about **3,000 in 2016** (in this sample). After 1992 the Summer and Winter Games moved to separate years, which is clearly visible in the charts.
- **Average age** peaked in the early 1900s (about 29 to 30), fell to its lowest point around **1980** (about 23.3), and has risen again to about **26**.
- **The USA** leads in participation and gold medals (747 gold medal rows before correcting for team events).
- **Basketball players** are the tallest on average (about **190.8 cm**). The tallest athlete in the data is **223 cm** and the heaviest is **214 kg**.
- **Height alone does not decide the medal type:** the height distributions for Gold, Silver and Bronze winners are almost identical.

Further results, such as top countries, top athletes, female participation and BMI by sport, are printed by the notebook as "Finding:" lines when you run it.

## 🗂️ Project Structure

```
olympics-analysis/
├── data/
│   └── dataset_olympics.csv
├── olympic_refined.ipynb
├── requirements.txt
└── README.md
```

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```

2. **Install the requirements**
   ```bash
   pip install -r requirements.txt
   ```

3. **Add the dataset** to a `data/` folder as `data/dataset_olympics.csv`.

4. **Open the notebook**
   ```bash
   jupyter notebook olympic_refined.ipynb
   ```
   Then choose **Kernel → Restart & Run All**.

### `requirements.txt`

```
pandas
numpy
matplotlib
seaborn
jupyter
```

## ⚠️ Limitations

- The data look like a **sample** of the full Olympic history, so totals may not match official medal tables.
- Each row is an athlete-event entry, so counts show entries rather than unique athletes unless stated.
- Height and weight are missing for roughly a quarter of rows, so those analyses use only the available data.
- Some historical NOC codes (such as `YUG`) no longer exist, so they appear as separate "countries".

## 🔮 Possible Next Steps

- Compare medals **per capita** or against population and GDP.
- Build a simple **machine learning model** to predict whether an athlete wins a medal.
- Create an interactive **dashboard** with Streamlit or Power BI.
- Study individual countries over time, or the effect of **hosting** the Games on medal counts.

## 👤 Author

**Vannovich**
- GitHub: [vannovich](https://github.com/vannovich)
- LinkedIn: [Awontu Vannovich Ndzifoin](https://www.linkedin.com/in/awontu-vannovich-ndzifoin-a629b4225/)

---

⭐ If you found this project useful, feel free to star the repository.
