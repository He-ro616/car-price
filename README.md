# Car Price Predictor

A Flask web application that estimates the resale price of a used car using a trained scikit-learn linear regression model.

## Features

- Predicts car prices in Indian rupees
- Uses manufacturer, model, purchase year, kilometres driven, and fuel type
- Responsive browser interface
- AJAX-based prediction without page reload
- Pretrained model and cleaned training data included

## Technology Stack

- Python 3
- Flask
- Flask-Cors
- pandas
- NumPy
- scikit-learn
- HTML, CSS, and JavaScript

## Project Structure

```text
.
|-- application.py                 # Flask application and prediction routes
|-- LinearRegressionModel.pkl      # Trained machine learning model
|-- Cleaned_Car_data.csv           # Cleaned vehicle dataset
|-- requirements.txt               # Python dependencies
|-- templates/
|   `-- index.html                 # Web interface
|-- static/
|   `-- style.css                  # Legacy styles
|-- "car price project1.ipynb"     # Model development notebook
`-- README.md
```

## Installation

1. Install Python 3.11 or a compatible version.

2. Open a terminal in the project directory and create a virtual environment:

   ```bash
   python -m venv .venv
   ```

3. Activate the virtual environment:

   On Windows:

   ```bash
   .venv\Scripts\activate
   ```

   On macOS or Linux:

   ```bash
   source .venv/bin/activate
   ```

4. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

## Running the Application

Start the Flask development server:

```bash
python application.py
```

Open `http://127.0.0.1:5000/` in a browser.

## Making a Prediction

1. Select a car manufacturer.
2. Select a car model.
3. Enter the purchase year.
4. Select the fuel type.
5. Enter the kilometres driven.
6. Click **Predict Car Price**.

The application sends the vehicle details to `/predict` and displays the estimated value.

## API Route

### `POST /predict`

Expects form data with these fields:

| Field | Description |
|---|---|
| `company` | Car manufacturer |
| `car_models` | Full car model name |
| `year` | Year of purchase |
| `fuel_type` | Petrol or Diesel |
| `kilo_driven` | Kilometres driven |

The response is a plain-text estimated price rounded to two decimal places.

## Model Information

The model is trained with the following features:

- `name`
- `company`
- `year`
- `kms_driven`
- `fuel_type`

The included notebook contains the model-training workflow and data-cleaning steps. Predictions are estimates and may differ from actual market prices.
