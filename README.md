# **YOLOv8_Car_Detection**
This repository demonstrate how to train car detection model using YOLOv8 on the custom dataset.
The goal is to detect cars in images and videos using Yolov8. I am using the "Car Detection Dataset" from Roboflow.

YOLOv8 is the latest state-of-the-art YOLO model and I will be using the version that developed by Ultralytics. Yolov8 is fast and easy to use with higher accuracy.

Google Colab provides free GPU resources for training deep learning models. This makes it an excellent platform for training models on large datasets that require significant computational power. In this repository, I will be using Google Colab for training. 

### **Training Custom Car Detection Model:**
1. Install ultralytics package
```
pip install ultralytics
```
2. Input Custom Dataset using Roboflow
```
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="YOUR_PROJECT")
project = rf.workspace("YOUR_WORKSPACE").project("YOUR_PROJECT")
dataset = project.version(X).download("yolov8")
```

3. YOLOv8 can be used in Command Line   
```
!yolo task=detect mode=train model=yolov8n.pt data={dataset.location}/data.yaml epochs=1 imgsz=640 plots=True
```
4. Run Inference with Trained Weights


### **Reference:**
1. https://github.com/ultralytics
2. https://github.com/roboflow
