# Automatic_License_Plate_Recognition
Using YOLOv8 for vehicle license plate detection and easyOCR for reading the license plate number.

## Dataset
The dataset for this project comprises 10,126 images sourced from Roboflow's [license plate recognition dataset](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e). These images come in various sizes, but for consistency, they were resized to 640x640 pixels. It's worth noting that Roboflow already provides pre-resized datasets, eliminating the need for additional resizing. Additionally, the dataset includes annotations that support YOLOv8's input requirements.

## Method
The method used for license plate recognition are
1. Using YOLOv8 for license plate detection (epoch = 50)
2. Crop the bounding box which license plate detected, and apply some preprocessing method.
3. Applying easyOCR to the preprocessed license plate image, to get license plate numbers.
4. Capture picture from web camera

## Performance
YOLOv8 for License Plate Object Detection
![image](https://github.com/synvialfajrine/Automatic_License_Plate_Recognition/assets/76579802/545c7d1e-add7-4cd7-9a2b-77fbeb0cc47a)
The confusion matrix above shows that 98% of the license plates are correctly predicted and only 2% are incorrectly predicted as license plates.

![image](https://github.com/synvialfajrine/Automatic_License_Plate_Recognition/assets/76579802/9a3a9934-8e2d-4f52-878d-e5fb440a93c1)


## Conclusion
The resulted segmentation model achieves high accuracy in detecting license plate as objects, but it struggles in recognizing all relevant characters in license plate number. 
## Reference
1. computervisioneng. 2023. [https://github.com/computervisioneng/automatic-number-plate-recognition-python-yolov8.git](https://github.com/computervisioneng/automatic-number-plate-recognition-python-yolov8.git)
2. Jocher, G., Chaurasia, A., & Qiu, J. (2023). YOLO by Ultralytics (Version 8.0.0) [Computer software]. https://github.com/ultralytics/ultralytics
3. Faishal, M. 2023. [https://github.com/MuhammadMoinFaisal/Automatic_Number_Plate_Detection_Recognition_YOLOv8.git](https://github.com/MuhammadMoinFaisal/Automatic_Number_Plate_Detection_Recognition_YOLOv8.git)
