# Day5MovieRecommender 🎬  
A Django web app that pulls movie data from **TMDb (The Movie Database)** and shows popular titles, movie details, and **recommendations**.

This project follows the build described in the accompanying write-up: “Day 5: Building a Movie Recommendation System with Django and TMDb API”.  

---

## Features
- **Popular movies** landing page (grid/list of trending/popular titles)
- **Movie detail page** with overview + poster
- **Recommendations** section (similar / recommended movies from TMDb)
- Poster images rendered using TMDb image base URL

---

## Tech Stack
- **Python**
- **Django**
- **TMDb API** (movie metadata + recommendations)

---

## Project Structure (high-level)
Typical layout for this repo:
- `MovieRecommendation/` – Django project root (contains `manage.py`)
- `movies/` – Django app for pages, templates, and TMDb integration
- `movies/utils.py` – helper to call TMDb endpoints and attach poster URLs

---

## Getting Started

### 1) Clone
```bash
git clone https://github.com/Mathurdanduprolu/Day5MovieRecommender.git
cd Day5MovieRecommender
```

### 2) Create & activate a virtual environment
```bash
python -m venv .venv
source .venv/bin/activate   # macOS/Linux
# .venv\Scripts\activate  # Windows (PowerShell)
```

### 3) Install dependencies
If the repo contains a `requirements.txt`, install from it:
```bash
pip install -r requirements.txt
```

If you don't have `requirements.txt`, the minimum packages for the tutorial build are:
```bash
pip install django requests
```

### 4) Add your TMDb API key
Create a TMDb key from your TMDb account settings.

Then set it in Django settings (quick tutorial-style approach):

**`MovieRecommendation/settings.py`**
```python
TMDB_API_KEY = "your_tmdb_api_key_here"
```

> Tip: In a real deployment, prefer environment variables instead of hardcoding secrets.

### 5) Run the app
From the folder that contains `manage.py`:
```bash
python manage.py runserver
```

Open:
- http://127.0.0.1:8000/ – Popular movies
- Click a movie → details page with recommendations

---

## How Recommendations Work
Recommendations are fetched directly from the TMDb endpoint:
- `movie/{movie_id}/recommendations`

So the “recommender” here is TMDb’s recommendation service, surfaced via Django pages.

---

## Screens / Demo
If you have a screen recording or screenshots, add them here (GitHub renders images nicely):

```md
![Home](docs/home.png)
![Detail](docs/detail.png)
```

---

## Roadmap / Ideas
- Search movies
- Pagination
- User accounts + watchlist
- Genre filters

---

## Credits
- Movie data powered by **TMDb**.
- Tutorial reference: Day 5 write-up on building the project with Django + TMDb API.
