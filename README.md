# 🎧 What Makes a Track Popular on Spotify?

**A Python-based exploratory data analysis project** — investigating whether a track's audio features (danceability, energy, loudness…) explain its popularity on Spotify. The analysis was performed using the public [Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset) from Kaggle.

---

## 📖 Introduction

My second portfolio project was focused on using Python for data analysis. As an aspiring data analyst, I wanted to continue building the toolkit a data analyst uses day to day. After learning and applying SQL to create and query an e-commerce database ([Olist E-Commerce Analysis](https://github.com/nicolascrifasi1603/olist-ecommerce-analysis)), the next step on the roadmap was learning how to use Python to perform an EDA (exploratory data analysis), before answering a business question. I picked the Spotify Tracks Dataset from Kaggle for this analysis.

---

## 🧠 Key Skills Demonstrated

| Skill | Where I used it |
|---|---|
| 🐍 **Basic Python programming** — loops, dictionaries, iterables | Built a `genre_to_bucket` dictionary mapping all 114 fine-grained genres into 10 broader genre families, then used a loop to sanity-check for any genres left unmapped. |
| 🧹 **Data cleansing with Pandas** | Checked for and handled missing values and duplicate rows — distinguishing true exact duplicates (removed with `duplicated()` across all columns) from `track_id` repeats caused by the same song appearing under multiple genre tags. These were kept since they reflected a real quirk of the dataset rather than an error. I also dropped unused columns. |
| 🔧 **Data transformation with Pandas** | Converted track duration from milliseconds to minutes, and used `str.split()` / `.explode()` to handle multi-artist tracks correctly when finding top artists. |
| 📊 **Data visualisation with Matplotlib & Seaborn** | Used a range of chart types depending on what the data called for — histograms for distributions, scatterplots for feature relationships, pie charts for category breakdowns, and an annotated correlation heatmap (`sns.heatmap(..., annot=True)`). |
| 🗂️ **Data segmentation** | Bucketed 114 genres into 10 genre families to compare audio profiles and popularity at a genre level, and isolated the top 1% most popular tracks as a separate segment. |
| 📈 **Descriptive statistics** | Used `.describe()` to profile audio features, examined distributions for spikes, outliers, and skew, and built a styled median-comparison table between the top 1% tracks and the full dataset. |
| 🔗 **Correlation analysis** | Measured correlation between each audio feature and popularity at both the whole-dataset level and within individual genre families, surfacing relationships (e.g. acousticness and popularity within Jazz/Blues) invisible in the aggregate data. |

---

## 🚀 Project Overview

For this project I gave myself an open-ended business question:

> **What makes a track popular on Spotify, and which audio features (energy, danceability, loudness…) are most strongly correlated between each other and with `popularity`?**

The goal of this project was to:

1. 🔍 Perform an EDA to better understand the dataset — which audio features exist, what are their distributions, what's the range of popularity, are they necessary for the analysis, and how does each correlate with popularity?
2. 🧹 Clean and transform the data as necessary to ensure the analysis is built on accurate and reliable data.
3. 📊 Create visualisations directly in Matplotlib and Seaborn to support the analysis.
4. 🧭 Explore different avenues to best answer an open-ended business question and arrive at a well-rounded answer.

---

## 🔄 Project Workflow

| Step | What I did |
|---|---|
| 📥 **Import & load** | Imported the dataset into a Jupyter notebook alongside the required packages (pandas, numpy, matplotlib, seaborn). |
| 👀 **Data understanding** | Got a first look at the data with `.shape`, `.head()`, `.dtypes`, and `.describe()`. |
| 🧹 **Data cleaning** | Checked for nulls and duplicates, distinguishing true exact duplicates from `track_id` repeats caused by the same song appearing under multiple genre tags, and dropped columns not needed for the analysis. |
| 📊 **Univariate analysis** | Ran a univariate analysis on popularity, key audio features, and genre counts to understand each variable on its own before comparing them. |
| 🗂️ **Genre segmentation** | Bucketed the 114 individual genres into 10 broader genre families to make genre-level comparisons interpretable. |
| 🔗 **Feature relationships** | Built a correlation heatmap to see how audio features relate to each other and to popularity across the whole dataset. |
| 🔎 **Deep dive 1** | *Does segmenting by genre family help us better understand relationships between audio features and popularity?* Segmented the correlation analysis by genre family, and found genre-specific relationships to popularity that were invisible at the whole-dataset level (e.g. acousticness and popularity within Jazz/Blues). |
| 🏆 **Deep dive 2** | *Can we find any common denominators of audio features across the most popular tracks in our dataset?* Isolated the top 1% most popular tracks and compared their audio feature medians, top artists, and top genres against the full dataset. |
| 💡 **Key findings** | Pulled everything together into a set of key findings answering the original business question. |

---

## 🗂️ Dataset Overview

- **Source:** [Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset) (Kaggle)
- **Size:** ~114,000 rows, 21 columns, spanning 114 genres (~1,000 tracks each)
- **Note:** each row is a *(track, genre)* pairing rather than a unique song, so the same track can appear more than once under different genre tags — a known quirk of the dataset that's accounted for throughout the analysis.

---

## 📁 Repository Structure

```
├── spotify_eda_python.ipynb     # Full analysis notebook
├── README.md
```

---

## 🛠️ How to Use This Project

1. **Clone the repo** and open it in Jupyter or VS Code.
2. **Download the dataset** from Kaggle (linked above) and place it in the project folder — it isn't included in this repo.
3. **Install the required packages** — pandas, numpy, matplotlib, seaborn.
4. **Run `spotify_eda_python.ipynb`** from top to bottom to reproduce the full analysis.
5. **Cross-reference the notebook** against the workflow and findings in this README to follow the reasoning behind each step.

---

## 🔗 Connect

If you'd like to discuss this project or data analytics roles, feel free to connect with me on [LinkedIn](http://www.linkedin.com/in/nicolascrifasi).
