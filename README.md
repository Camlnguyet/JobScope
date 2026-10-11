# Project Name: JobScope
A mini job search web app that lets you finds within a radius of X km around your location.
## Description
**Features**

- Search jobs by keyword, and filter by job type and salary range
- **Radius search**: pick a location (browser geolocation or a city) and a radius, and see only the jobs within that distance, sorted from nearest to farthest
- Pagination for search results
- Register, log in, and save favorite jobs
- Job CRUD (create, view, edit, delete)
- Sample data (~100 jobs) loaded from a CSV seed file

**How the radius search works**

Each job stores its `latitude` and `longitude`. The distance between the user and each job is computed with the Haversine formula, and jobs farther than the chosen radius and filtered out. No external map API is required.

**Tech stack**

- Backend: Python, Django
- Database: PostgreSQL (SQLite for local development)
- Frontend: HTML, CSS, JavaScript
- Tools: Git, GitHub

## Demo

- Live demo:
- Demo account:

|Search with radius|Job detail|
|---|---|
|||

## Prerequisites

- Python 3.11+
- pip and virtualenv (or venv)
- Git
- PostgreSQL 14+ (optional, SQLite is used by default for local development)

## Installation

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd jobscope

# 2. Create and activate a virtual environment 
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment variables
cp .env.example .env     # then edit .env (SECRET_KEY, DEBUG, ...)

# 5. Run migrations and load sample data
python manage.py migrate
python manage.py seed_jobs  # imports jobs from data/jobs.csv

# 6. Start the development server
python manage.py runserver
```

Open http://127.0.0.1:8000 in your browser.

## Usage

1. Open the home page and (optionally) allow location access, or choose a city
2. Enter a keyword, select a radius (e.g. 5/ 10 / 20 km) and click **Search**.
3. Browser results sorted by distance, then open a job to see its details.
4. Log in to save jobs and view them later in **Saved jobs**.

Run tests:

```bash
python manage.py test
```

## License
- MIT License
## Contact/ Credits
- Gmail: nhatnguyet.cam.freelancer@gmail.com
