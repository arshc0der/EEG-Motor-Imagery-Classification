# EEG Signal Analysis for Brain-Computer Interface (BCI)

## Dataset Download

This project uses the **EEG Motor Movement/Imagery Dataset (PhysioNet)**.

👉 Official dataset page:  
https://www.physionet.org/content/eegmmidb/1.0.0/#files-panel

### How to Download

1. Open the link above  
2. Download the dataset ZIP file  
3. Extract it  

After extraction, your folder should look like:

eegmmidb/
├── S001/
├── S002/
├── S003/
...

Each subject folder contains files like:
- S001R04.edf
- S001R08.edf
- S001R12.edf

---

## Important Note

- Dataset size: **~2.9 GB to 3.4 GB (uncompressed)**
- Do NOT upload dataset to GitHub

### Best Practice

- Download dataset separately
- Keep it local
- Add to `.gitignore`

---

## Quick Start

1. Download dataset from PhysioNet  
2. Extract it  
3. Place `eegmmidb/` in project folder  
4. Run:

python main.py

---

## Project Objective

- Analyze EEG signals
- Classify left vs right hand movement
- Build a Brain-Computer Interface (BCI) model

---

## Runs Used

- R04
- R08
- R12

Mapping:
- T1 → Left hand
- T2 → Right hand

---

## Project Structure

eeg_project/
│
├── eegmmidb/
├── results/
├── main.py
├── README.md
└── .gitignore

---

## Installation

pip install mne scikit-learn matplotlib numpy pandas scipy

---

## Virtual Environment (Optional)

python -m venv eeg_env
eeg_env\Scripts\activate
pip install mne scikit-learn matplotlib numpy pandas scipy

---

## What the Script Does

- Auto-detects EEG files
- Filters signals (8–30 Hz)
- Extracts features using CSP
- Trains LDA model
- Generates graphs and reports

---

## Output Files

results/
- raw_waveforms.png
- psd_plot.png
- left_vs_right_evoked.png
- confusion_matrix.png
- model_performance_report.txt
- demo_prediction.txt

---

## Model

- Feature extraction: CSP
- Classifier: LDA

---

## Notes

- Script skips bad files automatically
- Uses multiple subjects for better accuracy
- Works fully automatically once dataset is placed

---

## .gitignore Example

eegmmidb/
__pycache__/
*.pyc
eeg_env/
results/

---

## Internship Summary

This project demonstrates:
- EEG signal processing
- Feature extraction
- Machine learning classification
- Visualization of brain signals

---

## Author

arshc0der
