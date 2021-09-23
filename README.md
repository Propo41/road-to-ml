# Object Detection using Tensorflow

A repo containing my newbiew notes as I progress in my journey to learn Computer Vision.

The training part takes a long time since I didn't use CUDA for I have an AMD GPU. But I'll try using openGL instead. Hope that works.

Resources:
- https://youtu.be/yqkISICHH-U
- https://www.youtube.com/playlist?list=PLQVvvaa0QuDcNK5GeCQnxYnSSaar2tpku


To capture video data from screen:
```python
import numpy as np
import cv2
from PIL import ImageGrab

while True:
    img = ImageGrab.grab(bbox=(0, 0, 1366, 1100)) #x, y, w, h
    img_np = np.array(img)
    frame = cv2.cvtColor(img_np, cv2.COLOR_BGR2RGB)
    cv2.imshow("frame", frame)
    # pressing q will stop the loop
    if cv2.waitKey(1) & 0Xff == ord('q'):
        break
    
cv2.destroyAllWindows()
```

## Object Detection Project Valorant

- Precision is very low. Possible reason could be due to the high resolution of the images (1920\*1080) 
- May be fixed by using a low resolution and then while detecting the images in real time we can use the mouse pointer as the origin of the capture region
