#  Eye-Controlled Virtual Keyboard for Physically-Abled User Interaction

An assistive computer vision project that enables users to type using only eye movements and blinking. The system uses a webcam to track eye gaze and converts it into keyboard input, helping individuals with motor disabilities communicate easily.

---

##  Features
- Real-time eye tracking  
- Blink-based letter selection  
- Gaze-controlled navigation  
- Virtual on-screen keyboard  
- Audio feedback  

---

##  Technologies Used
- Python  
- OpenCV  
- Dlib  
- NumPy  
- Machine Learning concepts  

---

##  Project Directory Structure

```

Eye-Controlled-Virtual-Keyboard-for-Physically-Abled-User-Interaction/
│
├── eye_controlled.py
├── README.md
├── LICENSE
├── face_map.jpg
├── virtual_keyboard.png
└── final_output.png

````

---

##  How It Works
1. Webcam captures real-time video.  
2. Face and eye landmarks are detected using Dlib.  
3. Blink detection is performed using Eye Aspect Ratio (EAR).  
4. Gaze direction controls keyboard navigation.  
5. Blink selects highlighted letter.  

---

##  Installation

Download shape_predictor_68_face_landmarks.dat separately and place it in the project folder.

```bash
pip install opencv-python numpy dlib
````

---

##  Run the Project

```bash
python eye_controlled.py
```

---

## Sample Code

```python
import cv2
import dlib

detector = dlib.get_frontal_face_detector()
predictor = dlib.shape_predictor("shape_predictor_68_face_landmarks.dat")

cap = cv2.VideoCapture(0)

while True:
    _, frame = cap.read()
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    faces = detector(gray)

    for face in faces:
        landmarks = predictor(gray, face)
        cv2.putText(frame, "Face Detected", (20,40),
                    cv2.FONT_HERSHEY_SIMPLEX, 1, (0,255,0), 2)

    cv2.imshow("Frame", frame)
    if cv2.waitKey(1) == 27:
        break
```

---

##  Output Screenshots

### Face Landmark Mapping

![Face Map](face_map.jpg)

### Virtual Keyboard Interface

![Virtual Keyboard](virtual_keyboard.png)

### Final Output

![Final Output](final_output.png)

---

##  Future Enhancements

* NLP-based word prediction
* Multi-language support
* Voice output
* Mobile version

---

##  Conclusion

This project demonstrates a low-cost eye-controlled typing system using computer vision techniques, providing an effective assistive technology solution.

---
