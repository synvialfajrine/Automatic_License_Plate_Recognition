# Automatic_License_Plate_Recognition
Using YOLOv8 for vehicle license plate detection and easyOCR for reading the license plate number.

## How to Run
To run the code, simply open Google Colab or any Python Notebook-type editor and execute this following code:
 ``` from IPython.display import Image
try:
  filename = take_photo()
  print('Saved to {}'.format(filename))

  # Show the image which was just taken.
  display(Image(filename))
except Exception as err:
  # Errors will be thrown if the user does not have a webcam or if they do not
  # grant the page permission to access it.
  print(str(err)) ```

to capture image from webcam.
Next, execute this code to automatically process your images and obtain the license plate number:
```license_plate_detector(filename) ```
     
## Dataset
The dataset for this project comprises 10,126 images sourced from Roboflow's [license plate recognition dataset](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e). These images come in various sizes, but for consistency, they were resized to 640x640 pixels. It's worth noting that Roboflow already provides pre-resized datasets, eliminating the need for additional resizing. Additionally, the dataset includes annotations that support YOLOv8's input requirements.

## Method
This project is executed on Google Colaboratory. To set up the environment, the following libraries need to be installed: ```!pip install ultralytics``` and ```!pip install easyocr```. 
The license plate recognition process involves several steps: 
1. YOLOv8 is employed for license plate detection. YOLOv8 is trained for 50 epochs with 7058 train data.
2. Next, the bounding box containing the detected license plate is cropped and subjected to preprocessing techniques.
3. Subsequently, easyOCR is applied to the preprocessed license plate image to extract the license plate numbers.
4. Utilize a webcam to capture photos for testing the system's license plate prediction and recognition capabilities.

## YOLOv8 Performance
YOLOv8 for License Plate Object Detection
![image](https://github.com/synvialfajrine/Automatic_License_Plate_Recognition/assets/76579802/545c7d1e-add7-4cd7-9a2b-77fbeb0cc47a)
The confusion matrix above shows that 98% of the license plates are correctly predicted and only 2% are incorrectly predicted as license plates.

![image](https://github.com/synvialfajrine/Automatic_License_Plate_Recognition/assets/76579802/9a3a9934-8e2d-4f52-878d-e5fb440a93c1)

## Results
First we apply the license plate number recognition to moving cars video and get rather satisfactory results where the system able to detect all the license plate of all moving car, but has incosistency in extracting the license plate numbers.
[Click here to Watch the result Video](https://drive.google.com/file/d/1DtJlndfdCq7AA_ANuAnAj8nqqQZo-Uat/view?usp=share_link)

In the second attempt, photos featuring cars with visible license plates displayed on a phone screen were captured using a webcam. Subsequently, license plate number recognition was applied to these images.
![image](https://github.com/synvialfajrine/Automatic_License_Plate_Recognition/assets/76579802/bd250aeb-8094-480a-8470-940de0a24d8b)
The first captured image displays the license plate number "G241GH." The plate is successfully detected by the system, and each character in the license plate number is accurately recognized.

![image](https://github.com/synvialfajrine/Automatic_License_Plate_Recognition/assets/76579802/178d1ff6-339b-4536-90af-bd6cc0fef1ed)

In the image with the license plate number "G1023XX," the system accurately detects the plate but faces challenges in recognizing all characters correctly. Specifically, the character "G" is misinterpreted as "7," and "1" is mistaken for "4." Additionally, the characters "XX" are not recognized as part of the license plate. These inaccuracies could be caused by the image's brightness or quality, impacting the system's recognition accuracy.

## Conclusion
The object recognition model developed is accurate in detecting license plates and recognizing all characters in the license plate number. However, it's sensitive to image quality. If the image is too dark or has varying brightness, saturation, or contrast, the model might struggle to recognize the characters in the license plate. 

## Reference
1. computervisioneng. 2023. [https://github.com/computervisioneng/automatic-number-plate-recognition-python-yolov8.git](https://github.com/computervisioneng/automatic-number-plate-recognition-python-yolov8.git)
2. Jocher, G., Chaurasia, A., & Qiu, J. (2023). YOLO by Ultralytics (Version 8.0.0) [Computer software]. https://github.com/ultralytics/ultralytics
3. Faishal, M. 2023. [https://github.com/MuhammadMoinFaisal/Automatic_Number_Plate_Detection_Recognition_YOLOv8.git](https://github.com/MuhammadMoinFaisal/Automatic_Number_Plate_Detection_Recognition_YOLOv8.git)
