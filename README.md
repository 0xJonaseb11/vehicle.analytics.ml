# Vehicle Analytics - Django Machine Learning Project

A comprehensive web application for vehicle data analysis and machine learning predictions. This project demonstrates Exploratory Data Analysis (EDA), Regression, Classification, and Clustering using Django and popular Python ML libraries.

![Sample](./assets/Screenshot%202026-03-10%20at%2012.03.44.png)

## Project Structure

```text
VEHICLE-ANALYTICS/
├── config/                 # Django project configuration (settings, urls, wsgi, asgi)
├── predictor/              # Main Django app for ML predictions and data exploration
│   ├── data_exploration.py # Logic for EDA and data processing
│   ├── views.py            # View controllers for ML pages
│   ├── urls.py             # Route definitions for the app
│   └── templates/          # HTML templates for the dashboard
├── model_generators/       # Scripts for training and generating ML models
│   ├── regression/         # Price prediction model trainer
│   ├── classification/     # Income level classification model trainer
│   └── clustering/         # Client segmentation clustering model trainer
├── dummy-data/             # Dataset storage (CSV and GeoJSON)
├── manage.py               # Django management script
├── requirements.txt        # Project dependencies
└── venv/                   # Virtual environment (ignored by git)
```

## Prerequisites

- **Python 3.11+**
- **pip** (Python package manager)

## Dataset

The application utilizes the following datasets located in the `dummy-data/` directory:
- `vehicles_ml_dataset.csv`: Primary dataset for analysis and model training.
- `rwanda_districts.geojson`: Geospatial data for mapping (if applicable).

## Setup Instructions (macOS)

1.  **Clone the repository and navigate to the project folder:**
    ```bash
    cd VEHICLE-ANALYTICS
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run migrations (optional):**
    ```bash
    python manage.py migrate
    ```

## Running the Application

Start the Django development server:
```bash
python manage.py runserver
```

Once the server is running, access the dashboard at:
[http://127.0.0.1:8000/](http://127.0.0.1:8000/)

## Features & Analyses

### 1. Data Exploration (EDA)
- **URL:** `/data_exploration`
- View raw data samples and descriptive statistics to understand the vehicle dataset.

### 2. Regression (Price Prediction)
- **URL:** `/regression_analysis`
- Predict vehicle prices based on various features using a regression model.

### 3. Classification (Income Level)
- **URL:** `/classification_analysis`
- Classify vehicle owners into income categories based on their profiles.

### 4. Clustering (Client Segmentation)
- **URL:** `/clustering_analysis`
- Segment clients into "Economy", "Standard", or "Premium" groups using unsupervised learning.

## Machine Learning Models

Models are trained automatically upon the first visit to their respective analysis pages if the `.pkl` files are missing. The models are stored in:

- **Regression**: `model_generators/regression/regression_model.pkl`
- **Classification**: `model_generators/classification/classification_model.pkl`
- **Clustering**: `model_generators/clustering/clustering_model.pkl`

To retrain a model, simply delete the corresponding `.pkl` file and reload the page in your browser.

## Troubleshooting

- **Dataset Not Found**: Ensure `dummy-data/vehicles_ml_dataset.csv` exists.
- **Dependency Issues**: Run `pip install -r requirements.txt` again inside the activated `venv`.
- **Port Conflict**: If port 8000 is occupied, run:
  ```bash
  python manage.py runserver 8001
  ```

---
Built with ❤️ for Vehicle Analytics.