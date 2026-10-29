# Video Game Sales Analysis

## Project Overview

This project explores historical video game sales data for Ice, an online store that sells games worldwide. The goal is to identify patterns associated with commercial success and use those insights to support advertising and platform-selection decisions for a campaign planned for 2017.

The analysis considers game releases, platform life cycles, regional sales, genres, critic and user scores, and ESRB ratings. The dataset includes historical records through 2016, with the most recent period used to assess market trends.

## Business Objectives

- Identify platforms with the strongest sales performance and understand how platform popularity changes over time.
- Determine which platforms and genres may offer the greatest commercial potential.
- Explore the relationship between reviews and game sales.
- Compare gaming preferences across North America, Europe, and Japan.
- Test whether average user ratings differ between selected platforms and genres.

## Dataset

The notebook reads the dataset from `../data/games.csv`.

The main fields include:

| Column | Description |
|---|---|
| `name` | Video game title |
| `platform` | Platform the game was released on |
| `year_of_release` | Release year |
| `genre` | Game genre |
| `na_sales` | Sales in North America |
| `eu_sales` | Sales in Europe |
| `jp_sales` | Sales in Japan |
| `other_sales` | Sales in other regions |
| `critic_score` | Critics' score |
| `user_score` | Users' score |
| `rating` | ESRB age rating |

Sales values are represented in millions, as described in the source dataset.

## Tools and Technologies

- **Python**
- **Pandas** — data cleaning, transformation, and aggregation
- **Matplotlib** — data visualization
- **Seaborn** — statistical visualization
- **SciPy** — statistical hypothesis testing
- **Jupyter Notebook** — analysis and documentation

## Project Workflow

### 1. Data Preparation

- Standardized column names to lowercase.
- Converted release years and user scores to numeric data types.
- Treated values such as `TBD` in user scores as missing values so they would not interfere with numerical analysis.
- Reviewed missing values.
- Replaced missing ESRB ratings with an `Undefined` category for analysis.
- Calculated total sales across all regions for each game.

### 2. Exploratory Data Analysis

- Examined the number of games released over time.
- Compared sales across platforms and reviewed platform life cycles.
- Focused on the 2013–2016 period to better reflect the market relevant to the planned 2017 campaign.
- Compared platform sales distributions using box plots.
- Investigated relationships between critic/user scores and sales.
- Compared sales for the same games across different platforms.
- Evaluated sales distributions by genre.

### 3. Regional User Profiles

Compared the main platforms, genres, and ESRB rating categories in North America, Europe, and Japan to identify differences in regional preferences.

### 4. Hypothesis Testing

Two-sample Welch's t-tests were used with a significance level of `0.05`:

1. **Xbox One vs. PC user ratings** — tested whether the average user ratings were different.
2. **Action vs. Sports user ratings** — tested whether the average user ratings were different.

Welch's t-test was selected because the groups could have different sample sizes and variances.

## Key Findings

- **Platform life cycles are limited:** several older platforms, including the PS2, Wii, DS, Xbox 360, and PS3, experienced substantial declines in sales by 2016.
- **Recent data is more relevant:** the analysis focused on 2013–2016 to assess platforms and trends relevant to a 2017 campaign.
- **Potential platforms:** PS4, Xbox One, and Nintendo 3DS were identified in the notebook as platforms worth considering for investment.
- **Genre performance varies:** Shooter and Sports games showed stronger typical sales performance in the analysis, while Action games had a wide spread of outcomes, including high-selling outliers.
- **Regional preferences differ:** North America and Europe showed similar preferences for Action and Shooter games, while Role-Playing games and handheld consoles were particularly prominent in Japan.
- **Platform ratings:** the test did not find sufficient evidence of a difference between average user ratings for Xbox One and PC games (`p` approximately `0.15`).
- **Genre ratings:** the test found a statistically significant difference between average user ratings for Action and Sports games.

These findings describe the dataset and analysis in this notebook; they should not be interpreted as guarantees of future sales.

## Repository Structure

A suggested structure for publishing the project is:

```text
video-game-sales-analysis/
├── data/
│   └── games.csv
├── notebooks/
│   └── EDA.ipynb
└── README.md
```

Update the filenames above to match the actual structure of your repository. If the dataset is not included in the public repository, document where it came from and how to obtain it.

## How to Run the Project

1. Clone or download the repository.
2. Install the required libraries:

   ```bash
   pip install pandas matplotlib seaborn scipy jupyter
   ```

3. Make sure `games.csv` is available in the `data/` directory, or update the file path in the notebook.
4. Open the notebook in Jupyter Notebook or JupyterLab.
5. Run the cells from top to bottom.

## Skills Demonstrated

- Data cleaning and preparation
- Handling missing and non-numeric values
- Exploratory data analysis (EDA)
- Grouping and aggregation with Pandas
- Data visualization
- Regional and segment analysis
- Statistical hypothesis testing
- Translating analysis into business recommendations

## Conclusion

This project demonstrates how historical sales data, exploratory analysis, visualization, and statistical testing can support commercial decisions. The results highlight the importance of recent platform trends, genre performance, and regional preferences when planning marketing campaigns for video games.
