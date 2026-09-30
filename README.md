[README.md](https://github.com/user-attachments/files/32855976/README.md)
# Balkan Cinema — Data Mining & Clustering Analysis

A data mining project analysing ~14,000 Balkan films (1945–2025), built from scratch since no single Balkan movie database existed. The project was completed during an Erasmus+ exchange at the University of Ljubljana, Slovenia.

## What this project does

- **Builds a custom dataset** by combining four public sources (Wikidata, IMDb non-commercial datasets, a Kaggle/TMDb dataset, and the Lumiere Database), filtering out films that only appeared "Balkan" because they were dubbed in a Balkan language.
- **Analyses production trends** by country and year, showing the "golden age" of the 1960s–70s under communist-era state investment, the collapse after 1990, and the later recovery.
- **Breaks down genres** across the region, finding that drama dominates almost everywhere.
- **Compares ratings and popularity** (IMDb rating and vote counts) by country.
- **Clusters films with K-Means** (scikit-learn) on votes (log-scaled) and rating to separate *Blockbusters*, *Flops*, and — the most interesting group — *Hidden Gems*: highly-rated films almost nobody has heard of.
- **Compares average ratings across three historical eras**: Cold War / united Yugoslavia, the wars and transition of the 1990s, and the modern era.

## Interactive app

The repo also includes a Streamlit app (`app.py`) with two pages: a geographical map of Balkan film production with country-level stats and hidden gems, and a movie recommender using TF-IDF + cosine similarity on genre, director, and plot.

### How to run

1. Make sure `app.py` and `balkan_movies_confirmed.csv` are in the same folder.
2. Install dependencies:
   ```
   pip install streamlit pandas plotly numpy matplotlib scikit-learn
   ```
3. Run:
   ```
   streamlit run app.py
   ```
4. It will open automatically at `http://localhost:8501`.

## Tech stack

Python · pandas · numpy · matplotlib · seaborn · scikit-learn (KMeans, StandardScaler, TF-IDF, cosine similarity) · Streamlit · Plotly

## Example finding

Films like *The Vanishing World* (Yugoslavia, 9.5 rating) or *Wild Romania* (9.1) have excellent ratings but very few votes — exactly the kind of "hidden gem" the clustering step was built to surface.

## Motivation

All three of us on the team are from the Balkans, and wanted to explore why Balkan cinema remains internationally underrepresented — and to show that there's a lot of very good, very overlooked work in it.
