# Face-detection
 Real-Time Face Detection using OpenCV
This project is a simple real-time face detection system built using Python and OpenCV. It captures video from the user's webcam and uses a Haar Cascade Classifier to detect faces in the video stream. Detected faces are highlighted with green rectangles.

📌 Features
Real-time face detection from webcam

Uses pre-trained Haar cascade model

Highlights detected faces with bounding boxes

Minimal and efficient codebase

Press a to exit the video stream

Example Output
✅ The app will launch your webcam and start detecting faces. It looks like this:

diff
Copy
Edit
+---------------------------+
|                           |
|   [ Face Detected ]       |
|   [              ]        |
|                           |
+---------------------------+
Green rectangles will appear around any faces detected in the webcam feed.
🧪 Tech Stack
Python 3.x

OpenCV (cv2 library)

Haar cascade XML file (frontal face detection)

📁 File Structure
bash
Copy
Edit
Face_detection/
│
├── main.py                         # Main Python script
├── README.md                       # Project description
└── haarcascade_frontalface_default.xml  # Pre-trained model (optional)
🚀 How to Run
Install dependencies
Make sure you have OpenCV installed:

bash
Copy
Edit
pip install opencv-python
Run the project

bash
Copy
Edit
python main.py
Instructions

A window named "video_live" will open.

You’ll see green rectangles around any faces detected.

Press a key to exit the program.

🧠 Code Snippet
python
Copy
Edit
import cv2

face_cap = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
video_cap = cv2.VideoCapture(0)

while True:
    ret, video_data = video_cap.read()
    col = cv2.cvtColor(video_data, cv2.COLOR_BGR2GRAY)
    faces = face_cap.detectMultiScale(col, 1.1, 5)

    for (x, y, w, h) in faces:
        cv2.rectangle(video_data, (x, y), (x + w, y + h), (0, 255, 0), 2)

    cv2.imshow("video_live", video_data)
    if cv2.waitKey(10) == ord("a"):
        break

video_cap.release()
cv2.destroyAllWindows()
📌 Notes
The Haar cascade XML file is bundled with OpenCV. You don't need to download it manually.

This is a basic implementation suitable for learning or demo purposes.

Works on most systems with a webcam.

📷 Future Improvements (Optional)
Add face recognition using face_recognition library.

Save snapshots of detected faces.

Detect eyes, smiles, or other facial features.

Replace Haar cascades with deep learning-based models (like DNN or MTCNN).

Let me know if you'd like a custom GitHub repo title, thumbnail image, or license.
