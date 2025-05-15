# 📊 Sentiment Analysis on BRImo User Reviews

> A complete NLP pipeline project to scrape, clean, analyze, and visualize user reviews of the **BRImo** mobile application from Google Play Store.

---

## 📌 Overview

This project aims to perform **sentiment analysis** on the BRImo (BRI Mobile Banking) user reviews obtained from the **Google Play Store** using Natural Language Processing (NLP) techniques. It starts by **scraping user reviews**, then proceeds to **clean and preprocess** the data, **label the sentiment**, **train models**, and finally **visualize** the results to gain meaningful insights into user experiences.

---

## 🎯 Objectives

- ✅ Scrape up to 20,000 real user reviews of the BRImo app.
- 🧹 Preprocess text data to prepare for NLP tasks.
- 📊 Perform sentiment labeling (positive/negative/neutral).
- 🤖 Build and evaluate ML models for sentiment classification.
- 📈 Visualize sentiment trends and word frequency patterns.

---

## 🧰 Tech Stack

| Category          | Tools / Libraries                           |
|------------------|---------------------------------------------|
| Language         | Python                                      |
| Scraping         | `google-play-scraper`                       |
| Data Handling    | `pandas`, `numpy`                           |
| NLP              | `nltk`, `Sastrawi`, `scikit-learn`          |
| Visualization    | `matplotlib`, `seaborn`, `wordcloud`        |
| Modeling         | `Naive Bayes`, `SVM`, `Logistic Regression` |

---

## 🗂️ Project Structure

```

📁 sentiment-analysis-brimo
│
├── 📁 data                # Raw and cleaned data files (CSV)
├── 📁 models              # Trained ML models (joblib/pkl)
├── 📁 notebooks           # All Jupyter/Colab notebooks
│   ├── Scraping\_Data.ipynb
│   ├── Preprocessing.ipynb
│   └── Modeling.ipynb
├── 📁 visualizations      # Output graphs, wordclouds, etc.
├── 📄 README.md           # Project documentation
└── 📄 requirements.txt    # Python dependencies

````

---

## 🚀 How to Run

### 1. Clone the Repository

git clone https://github.com/username/sentiment-analysis-brimo.git
cd sentiment-analysis-brimo


### 2. Install Dependencies

pip install -r requirements.txt


### 3. Scrape Google Play Reviews

You can extract up to 20,000 reviews using the script below:

```python
from google_play_scraper import reviews, Sort
import pandas as pd

def scrape_brimo_reviews(count=20000, save_to_csv=True, filename='ulasan_brimo.csv'):
    try:
        print("🔍 Mengambil ulasan BRImo dari Google Play Store...")

        result, _ = reviews(
            'id.co.bri.brimo',
            lang='id',
            country='id',
            sort=Sort.NEWEST,
            count=count,
            filter_score_with=None
        )

        df = pd.DataFrame(result)

        if save_to_csv:
            df.to_csv(filename, index=False)
            print(f"✅ {len(df)} ulasan berhasil disimpan ke '{filename}'")

        return df

    except Exception as e:
        print(f"❌ Terjadi kesalahan saat mengambil ulasan: {e}")
        return None

# Run the scraping
df = scrape_brimo_reviews()
```

---

## 🧹 Preprocessing Steps

* ✅ **Case Folding** – convert all text to lowercase.
* ✅ **Tokenization** – split sentences into individual words.
* ✅ **Stopword Removal** – remove common but irrelevant words.
* ✅ **Stemming** – normalize words to their root forms.
* ✅ **Cleaning** – remove symbols, URLs, emojis, etc.

---

## 🧪 Modeling Techniques

The dataset is split into training and testing sets, and the following models are trained and evaluated:

* **Naive Bayes**
* **Logistic Regression**
* **Support Vector Machine (SVM)**
* **Random Forest**

**Evaluation Metrics:**

* Accuracy
* Precision
* Recall
* F1-Score

---

## 📈 Visualizations

* ✅ Pie chart of sentiment distribution
* ✅ Wordclouds for most frequent words in each sentiment
* ✅ Bar plots of top keywords
* ✅ Time-based sentiment trends

---

## 📁 Dataset Columns

| Column          | Description                |
| --------------- | -------------------------- |
| `userName`      | Reviewer’s name            |
| `content`       | Review text content        |
| `score`         | Rating (1-5 stars)         |
| `thumbsUpCount` | Likes for the review       |
| `at`            | Date and time of review    |
| `replyContent`  | Developer’s reply (if any) |

---

## 📌 Example Use Case

* 📉 **Product Feedback Analysis**: Track user sentiment over time to monitor app performance.
* 🏦 **Bank Decision Support**: Understand key pain points or feature requests.
* 📱 **UX Optimization**: Improve app usability based on real feedback.

---

## 🙋‍♂️ Author

**Nuruddin Sulthon Syah Fatahillah Rahmani**
*Machine Learning Graduate at Bangkit Academy 2024*
📧 [Email](mailto:adjikp76@gmail.com) | 🌐 [LinkedIn]([https://www.linkedin.com/in/nuruddin-sulthon/](https://www.linkedin.com/in/nuruddin-sulthon-syah-fatahillah-rahmani-35765829b/))

---
