import cv2

# Load trained Haar cascade
bin_cascade = cv2.CascadeClassifier('cascade.xml')

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    
    # Denoising
    frame_blur = cv2.bilateralFilter(frame, 15, 75, 75)
    gray = cv2.cvtColor(frame_blur, cv2.COLOR_BGR2GRAY)
    
    # Detection
    bins = bin_cascade.detectMultiScale(gray, scaleFactor=1.2, minNeighbors=5, minSize=(50, 50))
    
    for (x, y, w, h) in bins:
        cv2.rectangle(frame, (x,y), (x+w, y+h), (0, 0, 255), 2)
        cv2.putText(frame, 'Overflow Detected!', (x, y-10), cv2.FONT_HERSHEY_SIMPLEX, 0.8, (0, 0, 255), 2)
    
    cv2.imshow('Garbage Overflow Detector', frame)
    
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
# -
