# ANN Regression — Estimated Salary Prediction

A small end-to-end demo that uses an Artificial Neural Network (TensorFlow / Keras) to predict a customer's Estimated Salary based on features from the Churn_Modelling dataset. This repository contains the trained model and supporting encoders/scaler, Jupyter notebooks used for experimentation and prediction, and a Streamlit app for interactive inference.

## Stack
- **Language(s):** Jupyter Notebook (experiments & prediction), Python (app & utilities)
- **Framework / runtime:** TensorFlow (Keras), scikit-learn, Streamlit
- **Notable libraries:** tensorflow, scikit-learn, pandas, numpy, streamlit

## What’s in this repo
```
Churn_Modelling.csv            # Dataset (raw) used for training
experiments.ipynb              # Notebook with model training / experiments
prediction.ipynb               # Notebook showing a sample prediction workflow
app.py                         # Streamlit app for interactive prediction
model.h5                       # Trained Keras model (regression output)
label_encoder_gender.pkl       # LabelEncoder for gender
onehot_encoder_geography.pkl   # OneHotEncoder for geography
scaler.pkl                     # Preprocessor scaler (StandardScaler)
requirements.txt               # Python package requirements
README.md                      # This file
```

## Quick start — run the Streamlit app
1. Clone the repository and enter the directory:

```bash
git clone https://github.com/ssampathkumar104/ANN-Regression-Estimated-Salary.git
cd ANN-Regression-Estimated-Salary
```

2. Install dependencies (prefer a virtual environment):

```bash
python -m venv .venv
source .venv/bin/activate   # macOS / Linux
.\.venv\Scripts\activate  # Windows (PowerShell)

pip install -r requirements.txt
```

3. Launch the Streamlit app:

```bash
streamlit run app.py
```

Open the URL printed by Streamlit (usually http://localhost:8501) to interact with the app.

Notes:
- The app loads `model.h5`, `label_encoder_gender.pkl`, `onehot_encoder_geography.pkl`, and `scaler.pkl` from the repository root — keep these files next to `app.py`.
- The app expects the same input features used during training (CreditScore, Geography, Gender, Age, Tenure, Balance, NumOfProducts, HasCrCard, IsActiveMember, Exited).

## Notebooks
- experiments.ipynb — contains training code and model-building experiments.
- prediction.ipynb — demonstrates how to load the model, encoders and scaler, prepare a single sample, scale it and run a prediction.

If you want to re-train the model, open `experiments.ipynb` and follow the cells; the dataset `Churn_Modelling.csv` is included for convenience.

## Reproducing a single prediction (example)
Inside `prediction.ipynb` or the Streamlit app, you can provide the following example inputs to get an estimated salary:
- CreditScore: 600
- Geography: France
- Gender: Male
- Age: 40
- Tenure: 3
- Balance: 60000
- NumOfProducts: 2
- HasCrCard: 1
- IsActiveMember: 1
- Exited: 1

The trained model produces a numerical salary estimate (e.g., ~81715.82 in the notebook example).

## Next steps / Improvements
- Add a training script (e.g., train.py) to reproduce the full model-training pipeline from scratch.
- Add unit tests for preprocessing and a small CI workflow to check imports and notebook execution.
- Add more documentation about model metrics, hyperparameters and data preprocessing decisions.

## License
This repository does not include a license file. Add a LICENSE if you want to permit reuse.

## Contact
If you have questions or suggestions, open an issue or create a pull request.
