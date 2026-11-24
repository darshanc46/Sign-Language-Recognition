# Sign Language Recognition

A real-time sign language recognition web application. It reads hand gestures from a live webcam feed, classifies them with machine learning models, shows the result as text and can speak it aloud.

> **Team project** built by students of CMR University, Bengaluru.

<!-- Add 1-2 screenshots or a short demo GIF here, for example:
![Live recognition](docs/screenshot-recognition.png)
-->

## Features

- **Live recognition** from the webcam using MediaPipe hand landmarks
- **Four sign categories**, each with its own trained model:
  - Numbers (1-5)
  - Alphabets (A-Z)
  - Simple signs (CALL, DISLIKE, HI, LIKE, LOVE YOU, OK, PEACE, ROCK)
  - Custom signs (trained by the user from inside the app)
- **One-hand and two-hand** model variants
- **Text-to-speech** output using `pyttsx3`, with a switch to turn audio on or off
- **Landmark overlay** that can be turned on or off to see what MediaPipe detects
- **In-app training** of new custom signs
- Pages for Home, Supported Gestures, Sign Recognition, Custom Sign, Configuration and Documentation

## Tech Stack

| Area | Tools |
| --- | --- |
| Language | Python 3.10 |
| Web framework | Flask |
| Hand tracking | MediaPipe 0.10.9, OpenCV |
| Machine learning | Scikit-learn, Pandas, NumPy, Joblib |
| Speech | pyttsx3 |

## How It Works

1. OpenCV captures frames from the webcam.
2. MediaPipe detects the hand and extracts landmark keypoints.
3. The keypoints are normalised and passed to a Scikit-learn classifier for the selected category.
4. The predicted sign is shown on screen and, if audio is on, spoken with pyttsx3.

## Project Structure

```
app.py                 Flask app and routes
load_models.py         Loads trained models, normalisers and labels
file_structure.py      Folder/path helpers
preprocessing/
  image_processing.py  Frame and landmark processing
  process_keypoints.py Keypoint extraction and cleaning
  train_model.py       Model training
keypoints/             Keypoint datasets (CSV)
data/                  Custom sign data
final_models/          Trained models, normalisers and labels per category
static/                Images and static assets
requirements.txt       Python dependencies
```

## Getting Started

### Prerequisites
- Python 3.10 or 3.11
- A working webcam

### Installation

```bash
git clone <your-repository-url>
cd <repository-folder>

python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

pip install -r requirements.txt
```

### Run

```bash
python app.py
```

Open `http://127.0.0.1:5000` in your browser and allow camera access.

## Usage

1. Open **Sign Recognition** and allow the webcam.
2. Choose a sign category in **Configuration**.
3. Show a sign to the camera. The recognised text appears on screen.
4. Turn audio or the landmark overlay on or off using the switches.
5. To add your own sign, open **Custom Sign** and train a new model.

## Team

| Name | Contribution |
| --- | --- |
| Darshan C | _Add what you worked on, for example data collection, model training, Flask pages, speech feature_ |
| _Teammate name_ | _Contribution_ |

## Contact

**Darshan C** - [LinkedIn](https://www.linkedin.com/in/darshanc2003) - [GitHub](https://github.com/darshanc46)
