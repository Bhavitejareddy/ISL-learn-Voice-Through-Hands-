# ISL.learn — Indian Sign Language to Text

A real-time **Indian Sign Language (ISL)** recognition system that translates sign language into text. The project supports **fingerspelling alphabets**, **common words**, and **continuous sign language (CSL)** using **MediaPipe landmarks**, **classical machine learning**, and **deep learning** models.

---

## ✨ Features

- 🔤 Alphabet Recognition (A–Z)
- ✋ Common Word Recognition
- 📝 Continuous Sign Language (Sentence) Recognition
- 📷 Real-time webcam inference
- 🤖 Multiple ML and DL models (SVM, MLP, BiLSTM + Attention)
- ⚡ FastAPI backend
- 💻 React frontend with live camera preview

---

## 📂 Project Modes

| Mode | Notebook | Input | Model | Classes |
|------|----------|-------|--------|---------|
| Alphabet Recognition | `notebooks/alphabet.ipynb` | Single frame | SVM / MLP | 26 (A–Z) |
| Word Recognition | `notebooks/words.ipynb` | 60-frame clip (~2 seconds) | SVM / MLP / BiLSTM + Attention | 10 words |
| Sentence Recognition (CSL) | `notebooks/CSL.ipynb` | 60-frame clip per gloss | BiLSTM + Attention | 47 (21 words + A–Z) |

Each notebook demonstrates the complete pipeline:

- Data collection
- MediaPipe keypoint extraction
- Landmark normalization
- Model training
- Model evaluation
- FastAPI inference API

---

## 📁 Repository Structure

```text
ISL.learn/
│
├── notebooks/
│   ├── alphabet.ipynb
│   ├── words.ipynb
│   └── CSL.ipynb
│
├── server/
│   └── FastAPI inference application
│
├── frontend/
│   └── React application
│
├── models/
│   └── Trained .pkl and .pt files (gitignored)
│
├── data/
│   └── Extracted MediaPipe keypoints (.npz)
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🛠️ Installation

Clone the repository:

```bash
git clone https://github.com/<username>/ISL.learn.git
cd ISL.learn
```

Create a virtual environment:

```bash
python -m venv .venv
```

### Activate the environment

#### Windows

```bash
.venv\Scripts\activate
```

#### Linux / macOS

```bash
source .venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

---

## 📦 Requirements

```text
mediapipe
opencv-python
numpy
scikit-learn
torch
matplotlib
fastapi
uvicorn
pydantic
tqdm
```

Or simply run:

```bash
pip install -r requirements.txt
```

---

## 🚀 Running the Project

### 1. Train the Alphabet Model

Run:

```text
notebooks/alphabet.ipynb
```

This generates:

```text
models/alphabet_model.pkl
```

---

### 2. Train the Word Recognition Model

Run:

```text
notebooks/words.ipynb
```

This notebook records training videos through your webcam and generates:

```text
models/word_model.pt
```

---

### 3. Train the Sentence (CSL) Model

Run:

```text
notebooks/CSL.ipynb
```

This produces the sentence recognition model.

---

### 4. Start the FastAPI Server

```bash
uvicorn server.app:app --reload
```

---

### 5. Start the React Frontend

```bash
cd frontend
npm install
npm run dev
```

---

### 6. Launch the Application

1. Open the local URL shown by Vite.
2. Allow camera access.
3. Select one of the available modes:
   - Alphabet Recognition
   - Word Recognition
   - Sentence Recognition
4. Start signing in front of your webcam.

---

## 📥 Getting the Trained Models

The repository does **not** include:

- `.pt` model files
- `.pkl` model files
- `.npz` MediaPipe keypoint files

You can obtain them by:

- Running the notebooks to regenerate them, or
- Downloading them from the project release or Google Drive.

```text
Google Drive:
<Google Drive Link>

GitHub Releases:
<GitHub Release Link>
```

---

## 📊 Datasets

### Alphabet Dataset

- Folder-per-letter structure
- 26 classes (A–Z)
- Up to 350 images per class

### Word Dataset

Self-recorded using OpenCV.

- 10 words
- 30 video clips per word
- 60 frames per clip

### Sentence (CSL) Dataset

Self-recorded using OpenCV.

- 47 classes
- 30 video clips per class
- 60 frames per clip

---

## 🧠 Technology Stack

- MediaPipe (Hand + Face Landmarker)
- OpenCV
- NumPy
- Scikit-learn
- PyTorch
- FastAPI
- React
- Uvicorn

---

## 🔮 Future Improvements

- Expand the ISL vocabulary
- Transformer-based sequence models
- Real-time sentence generation
- Grammar correction using language models
- Mobile application support
- Cloud deployment

---

## 📄 License

This project is licensed under the **MIT License**.

Feel free to use, modify, and distribute this project for academic and research purposes.
