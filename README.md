# Spotify Catalog Insights 2025

Explored Spotify’s July 2025 API dataset of tracks, albums, and artists to reveal insights on trends in the world's largest digital music streaming platform. Combined SQL, Python, and data visualization to highlight patterns and historical changes in the music industry.

---

## 📊 Project Overview

The goal of this project was to perform end-to-end exploratory data analysis (EDA) on Spotify’s dataset to understand how various factors influence popularity on the platform.

Key highlights include:

- Cleaning and preparing millions of rows of track, album, and artist data.

- Visualizing music trends over time and across attributes.

- Demonstrating practical skills in SQL, Python (`pandas`, `seaborn`, `matplotlib`), and data storytelling.

---

## 📂 Datasets

The data was sourced from Spotify’s Web API (July 2025) and stored in PostgreSQL.
It consists of three core tables:

### `spotify_track`

Key fields:

- `durationms` – track length in milliseconds

- `explicit` – whether a track is flagged as explicit

- `trackid`, `albumid`, `name` – identifiers and metadata

Useful for analyzing song length distribution, explicit vs. non-explicit proportions, and word trends in track names.

### `spotify_album`

Key fields:

- `popularity` – Spotify’s popularity score for albums

- `totaltracks` – number of tracks per album

- `label` – record label associated with the album

- `releasedate` – release timing (used for historical trend analysis)

Enables exploration of album-level success factors, including label influence, release timing, and track counts.

### `spotify_artist`

Key fields:

- `popularity` – popularity score of artists

- `totalfollowers` – number of followers per artist

- `genres` – genre information for segmentation

- `lastsynctime` – timestamp of the last API sync

Provides artist-level insights and complements album and track analysis.

> [!NOTE]
> The included sample CSV datasets each containing 10,000 rows are included for testing and demonstration. To reproduce the full analysis, [download the complete SQL dumps from here](https://github.com/MusicMoveArr/Datasets) and restore it locally.

---

## 🔑 Key Analyses & Visualizations

The notebook explores several key questions:

**1. Track Length Distribution**

- Filtered songs to focus on those under 15 minutes (to reflect common listening ranges).

- Revealed most tracks peak just under ~200 seconds.

**2. Explicit vs. Non-Explicit Content**

- Pie chart showed explicit tracks make up 12.7% of the dataset.

**Trends in Track Names**

- Word cloud analysis of common words in track titles (e.g., “love”), excluding common modifiers like "remix" or "remastered".

**3. Album Popularity Trends**

- Box plot visualized the distribution of popularity scores across albums.

**4. Track Count vs. Popularity**

- Scatter plot revealed that albums between 10 to 20 tracks are the most popular.

**5. Label Performance**

- Identified top record labels by their average album popularity.

---

## 🛠️ Tech Stack

- **Languages:** Python (pandas, numpy, seaborn, matplotlib), SQL

- **Database:** PostgreSQL

- **APIs:** Spotify Web API (data source)

- **Visualization:** Matplotlib, Seaborn, WordCloud

- **Secrets Management:** `.env` file (for PostGreSQL access credentials)

---

## ⚙️ Setup Instructions

**1. Clone the repository**
```bash
git clone https://github.com/PKTrance/Spotify-Catalog-Insights.git
cd Spotify-Catalog-Insights
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Set up environment variables**

Use `.env.example` to create a `.env` file in the project root with your credentials:

```bash
DB_USER=your_username
DB_PASS=your_password
DB_HOST=localhost
DB_PORT=5432
```

**4. Open the notebook:**
```bash
jupyter notebook spotify-database-analysis-2025.ipynb
```

---

## 📁 Files
- `spotify-database-analysis-2025.ipynb`
- `spotify_track_sample.csv`
- `spotify_album_sample.csv`
- `spotify_artist_sample.csv`
- `.env.example`
- `requirements.txt`
- `figures/`

---

## 🙌 Acknowledgments

Special thanks to [MusicMoveArr](https://github.com/MusicMoveArr/Datasets) for sourcing and sharing the Spotify datasets used in this project.

---

## ✉️ Contact

Patrick Tran — `https://www.linkedin.com/in/patricktran22/` — patricktran@g.ucla.edu
