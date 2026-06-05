# TripWell AI Engineer

## Inclusive Tourism Accessibility Classification Using Deep Learning

<div align="center">

### Coding Camp 2026 powered by DBS Foundation

AI-Based Tourism Accessibility Classification System

</div>

---

## Overview

TripWell AI is a Natural Language Processing (NLP) system designed to classify Indonesian tourism reviews based on accessibility information for people with mobility limitations, including wheelchair users, elderly visitors, and families with strollers.

The system analyzes user-generated reviews and automatically predicts whether a tourist destination provides adequate accessibility facilities.

### Classification Categories

| Label | Category                               |
| ----- | -------------------------------------- |
| 1     | Ramah Disabilitas (Accessible)         |
| 0     | Akses Terbatas (Limited Accessibility) |

This AI component serves as the intelligence layer of the TripWell platform and supports inclusive tourism by providing accessibility insights from public reviews.

---

## AI Engineer Team

| Name                    | Role        |
| ----------------------- | ----------- |
| Laily Khoiriyah Isnaini | AI Engineer |
| Okky Puspa Ningrum      | AI Engineer |

---

## Project Objectives

Accessibility information in tourism destinations is often difficult to identify because relevant reviews are mixed with unrelated information such as scenery, ticket prices, food, and entertainment.

This project aims to:

* Automatically classify tourism reviews based on accessibility information.
* Assist users with mobility limitations in evaluating destinations before visiting.
* Support inclusive tourism through Artificial Intelligence and Natural Language Processing.
* Provide a scalable AI service that can be integrated into web applications.

---

## Dataset

### Data Collection

The dataset consists of Indonesian tourism reviews collected and manually labeled into accessibility categories.

### Data Labeling

| Label | Meaning           |
| ----- | ----------------- |
| 1     | Ramah Disabilitas |
| 0     | Akses Terbatas    |

### Text Preprocessing

Before training, several preprocessing steps were applied:

* Lowercasing
* Text cleaning
* Removing punctuation
* Removing numbers
* Stopword removal
* Tokenization
* Sequence encoding
* Sequence padding

These preprocessing stages help improve model performance and reduce noise within textual data.

---

## Model Architecture

The classification model was developed using TensorFlow and Keras Functional API with a Bidirectional Long Short-Term Memory (BiLSTM) architecture.

```text
Input Layer
↓
Embedding Layer
↓
SpatialDropout1D
↓
Bidirectional LSTM
↓
Bidirectional LSTM
↓
GlobalMaxPooling1D
↓
Dense Layer
↓
Dropout
↓
Output Layer (Sigmoid)
```

### Architecture Description

| Layer                | Function                                           |
| -------------------- | -------------------------------------------------- |
| Input Layer          | Receives tokenized review sequences                |
| Embedding Layer      | Converts words into dense vector representations   |
| SpatialDropout1D     | Reduces overfitting in embedding features          |
| Bidirectional LSTM   | Learns contextual information from both directions |
| GlobalMaxPooling1D   | Extracts the most important sequence features      |
| Dense Layer          | Learns higher-level representations                |
| Dropout              | Improves generalization and prevents overfitting   |
| Sigmoid Output Layer | Produces binary classification predictions         |

---

## Technologies Used

### Machine Learning & NLP

* Python
* TensorFlow
* Keras
* NumPy
* Pandas
* Scikit-Learn

### Model Deployment

* Flask
* Pickle

### Development Environment

* Google Colaboratory
* Jupyter Notebook
* GitHub

---

### File Description

| File                        | Description                                        |
| --------------------------- | -------------------------------------------------- |
| predict.py                  | Flask API for model inference                      |
| tripwell_bilstm_fixed.keras | Trained Bidirectional LSTM model                   |
| tokenizer.pkl               | Saved tokenizer used during training and inference |
| requirements.txt            | Python dependencies                                |
| README.md                   | AI Engineer documentation                          |

---

## Running the AI Service

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Start Flask API

```bash
cd app
python predict.py
```

The API will run on:

```text
http://localhost:5000
```

---

### Predict Accessibility Category

```http
POST /predict
```

Request:

```json
{
  "text": "Tempat wisata ini memiliki jalur kursi roda yang sangat baik."
}
```

Response:

```json
{
  "prediction": "Ramah Disabilitas",
  "confidence": 0.95
}
```

---

## Model Files

The trained model and tokenizer are stored separately.

| File                        | Description                    |
| --------------------------- | ------------------------------ |
| tripwell_bilstm_fixed.keras | Trained classification model   |
| tokenizer.pkl               | Tokenizer used during training |

### Model Download

https://drive.google.com/drive/folders/1cGS-OuZXDVINKzgCbOOyU1Cb-3sqMM38

---

## Sample Inference

```python
import requests

text = "Akses kursi roda tersedia dan jalannya rata"

response = requests.post(
    "http://localhost:5000/predict",
    json={"text": text}
)

print(response.json())
```

---

## AI Engineer Contributions

The AI Engineer team was responsible for:

* Designing the NLP workflow for accessibility classification.
* Preparing text preprocessing pipelines.
* Building and training the Bidirectional LSTM model.
* Performing model evaluation and validation.
* Implementing tokenizer and sequence processing.
* Exporting trained models for deployment.
* Developing a Flask-based inference API.
* Supporting integration between AI services and the TripWell web application.
* Conducting testing and prediction validation.

---

## Future Improvements

Potential enhancements for future development include:

* Larger and more diverse datasets.
* Multi-class accessibility classification.
* Transformer-based architectures such as IndoBERT.
* Explainable AI implementation.
* Real-time review analysis.
* Continuous model retraining pipeline.

---

## Project Information

| Item         | Description                                    |
| ------------ | ---------------------------------------------- |
| Project Name | TripWell                                       |
| Team ID      | CC26-PSU116                                    |
| Program      | Coding Camp 2026 powered by DBS Foundation     |
| Focus Area   | Inclusive Tourism Accessibility Classification |
| Domain       | Natural Language Processing (NLP)              |
| Model        | Bidirectional LSTM                             |
| Deployment   | Flask API                                      |

---

<div align="center">

Developed as part of Coding Camp 2026 powered by DBS Foundation

TripWell — Making Tourism More Accessible Through AI

</div>
