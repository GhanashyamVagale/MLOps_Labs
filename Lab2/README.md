# Logistic Regression API Service (FastAPI)

This lab builds a Logistic Regression classification model and serves it through a FastAPI application for real time predictions.

---

## Getting Started

### 1. Create a Virtual Environment

    python -m venv environment
    source environment/bin/activate   # Windows: environment\\Scripts\\activate

---

### 2. Install Required Packages

    pip3 install -r requirements.txt

---

## Train the Model

Navigate to the `src` directory and run the training script:

    cd src
    python3 train.py

After training completes, the serialized model will be saved inside the `model/` directory.

---

## Start the FastAPI Server

Run the following command from the project root (the directory containing `src`):

    uvicorn src.main:app --reload

The API will be available locally at:

    http://127.0.0.1:8000

---

## Interactive API Documentation (Swagger UI)

FastAPI automatically generates interactive API documentation.

To test the prediction endpoint:

1. Open your browser.
2. Visit:
       http://127.0.0.1:8000/docs
3. Locate the `/predict` endpoint.
4. Click "Try it out".
5. Replace the request body with the sample JSON below.
6. Click "Execute" to receive a prediction response.

---

## Example Request Payload

Use the following JSON body when testing the `/predict` endpoint:

```json
{
  "alcohol": 12.84,
  "malic_acid": 2.96,
  "ash": 2.61,
  "alcalinity_of_ash": 24.0,
  "magnesium": 101.0,
  "total_phenols": 2.32,
  "flavanoids": 0.60,
  "nonflavanoid_phenols": 0.53,
  "proanthocyanins": 0.81,
  "color_intensity": 4.92,
  "hue": 0.89,
  "od280_od315_of_diluted_wines": 2.15,
  "proline": 590.0
}
```
