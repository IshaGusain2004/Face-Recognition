
# 👤 Face Recognition Project using OpenCV

This is a basic real-time **Face Recognition System** built with Python and OpenCV. The project allows you to:

- Capture face samples from a webcam
- Train the LBPH (Local Binary Patterns Histograms) face recognition model
- Perform real-time face detection and recognition

---
## 📁 Project Structure
.
├── dataset.py # Script to collect face samples via webcam
├── training.py # Script to train the LBPH face recognizer
├── detection.py # Script to perform real-time face recognition
├── datasets/ # Folder storing collected face images
└── README.md # Project documentation

---

## ✅ Features

- Real-time face detection using Haar Cascades
- Model training using OpenCV's LBPH algorithm
- Face recognition with live webcam feed
- Confidence thresholding for accurate predictions

---

## 🧰 Requirements

- Python 3.x
- OpenCV (with contrib package)
- NumPy

### 🔧 Installation

Install the required libraries using pip:

```bash
pip install opencv-python opencv-contrib-python numpy

▶️ How to Use
Step 1: Collect Face Samples
Run dataset.py to capture 100 face images using your webcam.

bash
Copy
Edit
python dataset.py
This will open your webcam.

It will detect your face and save 100 grayscale face images into the datasets/ folder.

Press Enter key (key 13) to stop early if needed.

Step 2: Train the Model
Once you have collected face images, train the LBPH model:

bash
Copy
Edit
python training.py
The model reads images from datasets/

Trains and stores face data in memory (you can optionally save the model)

Step 3: Run Face Recognition
Run detection.py to detect and recognize faces in real-time:

bash
Copy
Edit
python detection.py
If the face is recognized with high confidence, it shows your name.

If not, it shows “Unknown”.

📌 Important Notes
Make sure to update these paths in your scripts:

python
Copy
Edit
# Haarcascade path
cv2.CascadeClassifier('C:/Python311/Lib/site-packages/cv2/data/haarcascade_frontalface_default.xml')

# Dataset path
data_path = 'C:/Users/Dell/Desktop/datasets/'
face_classifier.detectMultiScale(...) returns a list of faces. Avoid using if faces is ():, instead use:

python
Copy
Edit
if len(faces) == 0:
    return None
The confidence threshold (82%) can be adjusted in detection.py:

python
Copy
Edit
if confidence > 82:
    # Recognized
else:
    # Unknown

