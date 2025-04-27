# FairwAI-Bias-Detection-Project
This project focuses on detecting potential bias in hospitality-related Yelp reviews across five major cities, as part of the FairwAI Challenge. It includes extensive data cleaning, bias keyword detection, hotel chain analysis, and fairness impact measurements using statistical tests.

---
Dataset Link: https://www.kaggle.com/code/ypaudel/extensive-eda-on-yelp-business-data/input
---

# 📂 Data Folder

This folder is intended to store the raw Yelp data used in the project.

Due to the large size of the dataset (~7GB), the files are not directly hosted in this GitHub repository.  
You can download the original Yelp Open Dataset from [Kaggle - Yelp Dataset](https://www.kaggle.com/datasets/yelp/yelp-dataset).

Specifically used files:
- `yelp_academic_dataset_business.json`
- `yelp_academic_dataset_review.json`

These two files were filtered to focus on five cities (Las Vegas, Toronto, Phoenix, Charlotte, Pittsburgh) and hospitality-related categories.

---

## 🚀 Process Overview

1. **Data Filtering**:
    - Selected five target cities: Las Vegas, Toronto, Phoenix, Charlotte, and Pittsburgh.
    - Focused on hospitality categories: hotels, restaurants, spas, cafés, bars, etc.
    - Only included businesses with an average rating of **3.0 stars or higher**.

2. **Review Preprocessing**:
    - Cleaned text (lowercasing, punctuation/digit removal, stopwords filtering).
    - Built a custom **bias keyword lexicon** (50+ terms/phrases).
    - Flagged reviews containing bias-related language, but **only** among **low-rated (1-2 star)** reviews for greater precision.

3. **Hotel Chain Detection**:
    - Identified major chains (Hilton, Marriott, Holiday Inn, etc.) using a substring search in business names.
    - Added 'is_chain_hotel' and 'hotel_chain' flags for analysis.

4. **Statistical Testing**:
    - Chi-square tests (including Yates correction) for bias rate differences.
    - Two-proportion Z-tests between individual hotel chains and peers.
    - Disparate Impact analysis for city-wise and chain-wise fairness evaluation.

5. **Visualization**:
    - Created visual plots to compare review counts and bias rates across cities and chains.

6. **Bonus**:
    - Discussed potential for using machine learning (e.g., DistilBERT) to automate bias detection.
    - Reflected on ethical considerations and responsible AI practices.

---

## 📊 Key Results

- **Bias rate in chain hotels** was roughly **twice** that of non-chain businesses.
- **Statistically significant** bias differences were found across several hotel brands and cities.
- **Disparate Impact** was observed, with certain brands and cities exceeding fairness thresholds.

---

## 🛡 Ethical Considerations

- Automation risks (false positives/negatives) must be managed carefully.
- Human oversight should accompany any automated flagging system.
- Transparency and explainability are crucial when labeling businesses.

---

## ⚡ Technologies Used

- Python 3.9
- Pandas
- Numpy
- Scipy
- Statsmodels
- Matplotlib
- Regex (for bias detection)
- NLTK (stopword removal)

---

## 🧠 Author

- Mustafa Poonawala  
  FairwAI Challenge Participant | Data Science Enthusiast

---

## 📄 License

This project is intended for educational and research purposes under the FairwAI Challenge guidelines.

