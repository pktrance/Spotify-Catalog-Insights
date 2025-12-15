# Spotify Catalog Insights 2025

Analyzed 2M+ catalog records from Spotify's platform to uncover strategic patterns in label performance, artist concentration, and album composition. This project demonstrates end-to-end data analysis using Python and SQL to derive actionable insights for the music industry.

---

## Project Overview

This project performs comprehensive exploratory data analysis on Spotify's catalog data to understand competitive dynamics in digital music streaming. The analysis focuses on strategic business insights that challenge conventional assumptions about the music industry.

---

## Dataset Structure

The data was sourced from Spotify's Web API (July 2025) and consists of three core tables stored in PostgreSQL:

### `spotify_track`

Key fields:

- **Key fields:** `trackid`, `albumid`, `name`, `durationms`, `explicit`

- **Purpose:** Track-level attributes including duration and content ratings

- **Records:** 2,128,954 tracks

### `spotify_album`

Key fields:

- **Key fields:** `popularity`, `totaltracks`, `name`, `label`, `releasedate`

- **Purpose:** Album-level success metrics and metadata

- **Records:** 252,790 albums across 27,635 labels

### `spotify_artist`

Key fields:

- **Key fields:** `popularity`, `totalfollowers`, `genres`, `lastsynctime`

- **Purpose:** Artist-level popularity and audience metrics

- **Records:** 15,872 artists

### Data Integrity

- No missing values in critical fields

- Minimal duplicates after initial data quality checks

> [!NOTE]
> The included sample CSV datasets each containing 10,000 rows are included for testing and demonstration. To reproduce the full analysis, [download the complete SQL dumps here](https://github.com/MusicMoveArr/Datasets) and restore it locally.

---

## Analysis Approach

This project combines SQL and Python to analyze strategic patterns across three key dimensions:

**1. Label Performance** – Tested whether catalog size correlates with success by grouping labels 
into size categories and comparing average album popularity. Found that mid-size independent labels 
(50-199 albums) achieve 51% higher performance than major labels, suggesting strategic curation 
outperforms volume.

**2. Artist Concentration** – Examined success distribution by grouping artists into popularity 
tiers and measuring engagement per tier. Revealed that top 5% of artists (60+ popularity) achieve 
4x higher per-album engagement, indicating platform winner-takes-all dynamics.

**3. Album Composition** – Analyzed relationship between track count and popularity to identify 
optimal album length. Found non-linear pattern with 13-16 track albums performing best, contradicting 
simple "shorter is better" hypothesis.

**Technical Implementation:** Used SQL (PostgreSQL) to merge normalized tables and extract data, 
then Python (Pandas) for categorical grouping, aggregation, and visualization. 

For detailed SQL queries, data transformations, and visualization code, [see the Jupyter notebook](https://github.com/pktrance/Spotify-Catalog-Insights/blob/main/spotify-database-analysis-2025.ipynb).

---

## Key Findings

The notebook explores several key questions:

**1. Mid-Size Label Advantage**

- Mid-size independent labels (50-199 albums) achieve 51% higher average album popularity compared to major labels (500+ albums)

- Demonstrates that focused artist development and niche specialization outperform volume-based catalog strategies

- Challenges the assumption that bigger labels automatically win
  
**2. Platform Concentration Dynamics**

- Top 5% of artists (those with 60+ popularity scores) achieve 4.3x higher per-album engagement than the remaining 95% of artists

- Only 860 artists out of 15,800+ drive disproportionate platform success

- Reveals winner-takes-all dynamics where established artists compound their advantages

**3. Album Composition Patterns**

- Albums with 13-16 tracks show highest popularity (13.44 avg)

- Non-linear relationship contradicts simple "shorter is better" hypothesis

- EP albums (≤8 tracks) significantly underperform, possibly due to promotional nature
  
**Technical Highlights**

- Processed and merged 2M+ catalog records across multiple normalized tables

- Combined SQL (PostgreSQL) for data extraction and Python (Pandas) for complex analysis

- Created multi-dimensional aggregations to reveal patterns across label size, artist tiers, and album composition

- Built visualizations to communicate findings to non-technical stakeholders

---

## Visualizations

The project includes several key visualizations:

**1. Label Performance Analysis**
<br>![Label Size vs Performance](figures/label_performance.png)
<br>*Mid-size independent labels (50-199 albums) achieve 51% higher average album popularity 
than major labels, demonstrating competitive advantage through focused curation.*

**2. Artist Concentration Dynamics**
<br>![Artist Distribution](figures/artist_concentration.png)
<br>*Platform shows significant success concentration: top 5% of artists achieve 4x higher 
per-album engagement despite representing small fraction of catalog.*

**3. Album Composition Patterns**
<br>![Album Length Analysis](figures/album_length_scatter.png)
<br>*Non-linear relationship between track count and popularity, with 13-16 track albums 
showing optimal performance.*

**4. Track Duration Distribution**
<br>![Track Duration](figures/duration_histogram.png)
<br>*Majority of tracks concentrate around 180-210 seconds, aligning with playlist preferences.*

**5. Album Popularity Distribution**
<br>![Popularity Box Plot](figures/popularity_boxplot.png)
<br>*Box plot reveals popularity score distribution and outlier identification.*

**6. Content Strategy**
<br>![Explicit Content](figures/explicit_pie.png)
<br>*12.7% of catalog is explicit content, with strategy varying by genre and audience.*

---

## Technical Stack

### Languages & Tools:

- **Python 3.11+:** Primary analysis environment
  - `pandas` – data manipulation and aggregation
  - `numpy` – numerical operations
  - `matplotlib` & `seaborn` – visualization
  - `psycopg2` – PostgreSQL connectivity

- **SQL (PostgreSQL 15+):** Data storage and extraction
  - Complex JOINs across normalized tables
  - Window functions for ranking and aggregation
  - CTEs for multi-step queries

### Environment:

- Jupyter Notebook for exploratory analysis and visualization
  
- `.env` file for credentials management (not committed to repo)

- Git for version control

---

## Setup Instructions

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

## Files
- `spotify-database-analysis-2025.ipynb`
- `spotify_track_sample.csv`
- `spotify_album_sample.csv`
- `spotify_artist_sample.csv`
- `.env.example`
- `requirements.txt`
- `figures/`

---

## Acknowledgments

Special thanks to [MusicMoveArr](https://github.com/MusicMoveArr/Datasets) for sourcing and sharing the Spotify datasets used in this project.

---

## Contact

Patrick Tran — `https://www.linkedin.com/in/patricktran22/` — patricktran@g.ucla.edu
