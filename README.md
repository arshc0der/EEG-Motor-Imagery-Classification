
# 🧠 EEG Motor Imagery Classification
### Brain-Computer Interface (BCI) Signal Analysis using CSP + LDA

<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/preview/preview.png" width="90%" alt="EEG Motor Imagery Classification Image"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-Completed-brightgreen.svg" />
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Notebook-Jupyter-orange?logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/EEG-BCI-purple" />
  <img src="https://img.shields.io/badge/Dataset-PhysioNet-red" />
  <img src="https://img.shields.io/badge/Signal%20Processing-MNE-blueviolet" />
  <img src="https://img.shields.io/badge/ML-scikit--learn-f7931e?logo=scikitlearn&logoColor=white" />
  <img src="https://img.shields.io/badge/Feature%20Extraction-CSP-success" />
  <img src="https://img.shields.io/badge/Classifier-LDA-informational" />
  <img src="https://img.shields.io/badge/Accuracy-46.67%25-yellow" />
  <img src="https://img.shields.io/github/license/arshc0der/EEG-Motor-Imagery-Classification?color=green" />
  <img src="https://img.shields.io/github/stars/arshc0der/EEG-Motor-Imagery-Classification?style=social" />
  <img src="https://img.shields.io/github/forks/arshc0der/EEG-Motor-Imagery-Classification?style=social" />
  <img src="https://img.shields.io/github/issues/arshc0der/EEG-Motor-Imagery-Classification" />
  <img src="https://img.shields.io/github/last-commit/arshc0der/EEG-Motor-Imagery-Classification" />
</p>

---

## 🚀 Overview

This project performs **EEG signal analysis for Brain-Computer Interface (BCI)** applications using the **EEG Motor Movement/Imagery Dataset** from **PhysioNet**.

The goal is to classify **left-hand vs right-hand motor imagery** from EEG recordings by applying:

- **Band-pass filtering (8–30 Hz)**
- **Common Spatial Patterns (CSP)** for feature extraction
- **Linear Discriminant Analysis (LDA)** for classification

It is designed as a practical machine learning + signal processing project that demonstrates the full EEG workflow from **raw EDF files to prediction, evaluation, and visualization**.

---

## 🎯 Project Objective

- Analyze real EEG motor imagery signals
- Classify **left vs right hand movement**
- Build a simple **BCI classification pipeline**
- Visualize waveforms, PSD, evoked responses, and confusion matrix
- Generate prediction and model performance reports automatically

---

## 📊 Final Results

### Model Summary
- **Subjects used:** 20
- **Runs used:** `R04`, `R08`, `R12`
- **Reference sampling frequency:** `160.0 Hz`
- **Total valid EDF files loaded:** `60`
- **Total skipped files:** `0`
- **Epoch window:** `1.0 to 4.0 sec`
- **Accuracy:** `0.4667`

### Classification Report

```text
              precision    recall  f1-score   support

        left       0.47      0.49      0.48        91
       right       0.46      0.44      0.45        89

    accuracy                           0.47       180
   macro avg       0.47      0.47      0.47       180
weighted avg       0.47      0.47      0.47       180
````

### Demo Prediction

```text
Predicted: right
Actual: left
```

> **Note:** This repository currently represents a **baseline EEG motor imagery classifier**.
> The present accuracy shows that motor imagery EEG decoding is challenging and can likely be improved with better preprocessing, channel selection, feature engineering, and more advanced models.

---

## 🧠 Dataset

This project uses the **EEG Motor Movement/Imagery Dataset (EEGMMIDB)** from PhysioNet.

🔗 Official dataset page:
[PhysioNet EEG Motor Movement/Imagery Dataset](https://www.physionet.org/content/eegmmidb/1.0.0/)

<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/preview/1.png" width="90%" alt="PhysioNet Site Image"/>
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/preview/2.png" width="90%" alt="PhysioNet Site Download Section Image"/>
</p>

### Runs Used

* `R04`
* `R08`
* `R12`

### Event Mapping

* **T1 → Left hand**
* **T2 → Right hand**

---

## 📥 Dataset Download

### How to Download

1. Open the PhysioNet dataset link above
2. Download the dataset ZIP
3. Extract it
4. Place the extracted folder inside the project root

Expected structure:

```text
eegmmidb/
├── S001/
├── S002/
├── S003/
...
```

Each subject folder contains files such as:

```text
S001R04.edf
S001R08.edf
S001R12.edf
```

---

## ⚠️ Important Note

* Dataset size is approximately **2.9 GB to 3.4 GB**
* **Do NOT upload the dataset to GitHub**
* Keep the dataset stored locally
* Add it to `.gitignore`

---

## 🏗 Project Structure

```text
EEG-Motor-Imagery-Classification/
│
├── eegmmidb/                     # Local dataset folder (not pushed to GitHub)
├── results/                     # Generated plots and reports
│   ├── raw_waveforms.png
│   ├── psd_plot.png
│   ├── left_vs_right_evoked.png
│   ├── confusion_matrix.png
│   ├── model_performance_report.txt
│   └── demo_prediction.txt
│
├── main.ipynb                   # Main notebook / workflow
├── README.md
├── LICENSE
├── .gitignore
└── .gitattributes
```

---

## ⚙️ Installation

Install required dependencies:

```bash
pip install mne scikit-learn matplotlib numpy pandas scipy
```

### Optional Virtual Environment

```bash
python -m venv eeg_env
```

#### Windows

```bash
eeg_env\Scripts\activate
```

#### Linux / macOS

```bash
source eeg_env/bin/activate
```

Then install packages:

```bash
pip install mne scikit-learn matplotlib numpy pandas scipy
```

---

## ▶️ Quick Start

1. Download the EEGMMIDB dataset from PhysioNet
2. Extract it
3. Place `eegmmidb/` in the project folder
4. Run the notebook or script pipeline

If using Python script version:

```bash
python main.py
```

If using notebook version:

```bash
jupyter notebook
```

Open `main.ipynb` and run all cells.

---

## 🔬 Processing Pipeline

The workflow includes:

1. **Auto-detection of EEG EDF files**
2. **Loading multi-subject EEG recordings**
3. **Band-pass filtering between 8–30 Hz**
4. **Epoch extraction for motor imagery segments**
5. **Feature extraction using CSP**
6. **Classification using LDA**
7. **Evaluation with confusion matrix and classification report**
8. **Visualization of EEG characteristics**
9. **Demo prediction generation**

---

## 🧰 Tech Stack

* **Python**
* **MNE**
* **NumPy**
* **Pandas**
* **SciPy**
* **Matplotlib**
* **scikit-learn**

---

## 📈 Output Files

The project generates the following outputs:

```text
results/
├── raw_waveforms.png
├── psd_plot.png
├── left_vs_right_evoked.png
├── confusion_matrix.png
├── model_performance_report.txt
└── demo_prediction.txt
```

---

## 🖼 Visual Results

### Raw EEG Waveforms

<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/raw_waveforms.png" width="90%" alt="Raw EEG Waveforms"/>
</p>

### Power Spectral Density (PSD)

<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/psd_plot.png" width="90%" alt="PSD Plot"/>
</p>

### Left vs Right Evoked Response

<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/left_vs_right_evoked.png" width="90%" alt="Left vs Right Evoked Response"/>
</p>

### Confusion Matrix

<p align="center">
  <img src="https://raw.githubusercontent.com/arshc0der/EEG-Motor-Imagery-Classification/refs/heads/main/results/confusion_matrix.png" width="70%" alt="Confusion Matrix"/>
</p>

---

## 📝 Files Used in Training

The model used **60 EDF files** from **20 subjects**, covering:

* `S001` to `S020`
* Runs `R04`, `R08`, `R12`

This gives:

* **20 subjects × 3 runs = 60 EDF files**

No files were skipped in this run.

---

## 📌 Example Used Files

```text
eegmmidb\S001\S001R04.edf
eegmmidb\S001\S001R08.edf
eegmmidb\S001\S001R12.edf
...
eegmmidb\S020\S020R04.edf
eegmmidb\S020\S020R08.edf
eegmmidb\S020\S020R12.edf
```

---

## 🧪 Model

### Feature Extraction

* **Common Spatial Patterns (CSP)**

### Classifier

* **Linear Discriminant Analysis (LDA)**

This combination is commonly used in classical BCI pipelines and provides a good baseline for motor imagery EEG classification.

---

## ✅ What This Project Demonstrates

* EEG signal preprocessing
* Frequency filtering
* Multi-subject dataset handling
* Epoch-based feature extraction
* Classical machine learning for BCI
* Evaluation using confusion matrix and classification report
* EEG data visualization

---

## ⚡ Current Limitations

* Baseline accuracy is still relatively low
* Only classical CSP + LDA pipeline is used
* More advanced channel selection and artifact removal are not yet included
* Deep learning models are not yet explored
* Hyperparameter tuning is limited

---

## 🛣 Future Improvements

* [ ] Add artifact removal / ICA preprocessing
* [ ] Improve channel selection strategy
* [ ] Tune CSP and LDA parameters
* [ ] Compare with SVM / Random Forest / XGBoost
* [ ] Try CNN / Deep Learning approaches
* [ ] Add subject-wise evaluation
* [ ] Add train/test split reproducibility controls
* [ ] Add better experiment tracking

---

## 📄 .gitignore Example

```gitignore
eegmmidb/
__pycache__/
*.pyc
eeg_env/
results/
```

---

## 🤝 Contributing

Contributions, improvements, and suggestions are welcome.

If you'd like to improve the preprocessing pipeline, model performance, or visualizations, feel free to fork the repository and open a pull request.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**arshc0der**

---

## 🌟 Repository Summary

This project is a practical implementation of:

* **EEG signal analysis**
* **Motor imagery classification**
* **Brain-Computer Interface (BCI) basics**
* **Feature extraction with CSP**
* **Machine learning with LDA**
* **Scientific visualization of brain signals**

If you found this project useful, consider giving it a **star** on GitHub.

