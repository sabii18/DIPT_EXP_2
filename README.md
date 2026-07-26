# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.14  
- Jupyter Notebook 
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** SABEESHWARAN. P  

### Register No: 212225230234 
**Date:** 26.07.2026

```python
import cv2
cap = cv2.VideoCapture(0)
if not cap.isOpened():
    print("Cannot Open WebCam")
    exit()
while True:
    ret, frame = cap.read()

    if not ret:
        print("Can't Capture Frame")
        break

    cv2.imwrite("Captured_frame.jpg",frame)
    
    cv2.imshow("Live Video",frame)

    resized = cv2.resize(frame,(640,480))
    cv2.imshow("Resized Video",resized)

    rotated = cv2.rotate(frame,cv2.ROTATE_90_CLOCKWISE)
    cv2.imshow("Rotated Video",rotated)
    
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

<img width="1338" height="793" alt="image" src="https://github.com/user-attachments/assets/1f123337-b03f-4a4f-be49-945be5d8fc00" />

<img width="1917" height="1018" alt="image" src="https://github.com/user-attachments/assets/e820649f-e373-4f9f-b61d-90f742d8321e" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
