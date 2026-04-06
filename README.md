# Student Management System

A Flask web application for managing student records with a built-in ML-based performance prediction feature.

![Dashboard](media/Dashboard%20with%20students%20and%20live%20statistics.jpg)

## Features

- Admin login with session-based authentication
- Add, edit, delete, and search student records
- Live dashboard stats (total students, departments, final-year count)
- ML-powered pass/fail prediction based on marks (Logistic Regression)

## Tech Stack

- Python / Flask
- SQLite
- scikit-learn
- Jinja2 templates + CSS

## Project Structure

```
├── app.py              # Main Flask app and routes
├── auth.py             # Login/logout blueprint
├── models.py           # DB query functions
├── database.py         # SQLite connection and table setup
├── ml_model.py         # Train and save the ML model
├── model.pkl           # Saved logistic regression model
├── create_admin.py     # Script to create the admin user
├── seed_students.py    # Script to seed sample student data
├── templates/          # HTML templates
├── static/             # CSS styles
└── students.db         # SQLite database
```

## Getting Started

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Train and save the ML model:

```bash
python ml_model.py
```

3. Create the admin user:

```bash
python create_admin.py
```

4. (Optional) Seed sample student data:

```bash
python seed_students.py
```

5. Run the app:

```bash
python app.py
```

Then open `http://127.0.0.1:5000` in your browser.

## Login

Default credentials (set in `create_admin.py`):

- Username: `admin`
- Password: `admin123`

Change the password in `create_admin.py` before running it in any non-local environment.

## ML Prediction

The prediction model uses logistic regression trained on a simple marks dataset. A score of 50 or above predicts a PASS. To retrain the model, edit `ml_model.py` and re-run it.

## Screenshots

| Login | Dashboard |
|-------|-----------|
| ![Login](media/login_pg.jpg) | ![Dashboard](media/empty_admin_dashboard.jpg) |

| Add Student | Prediction |
|-------------|------------|
| ![Add](media/Add%20new%20student%20form.jpg) | ![Predict](media/Machine%20learning%E2%80%93based%20student%20performance%20prediction.jpg) |
