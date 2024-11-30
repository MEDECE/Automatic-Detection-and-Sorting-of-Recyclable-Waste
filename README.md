Waste Detection and Classification using YOLOv8

1. Project Results and Overview

Overview

This project aims to automate waste sorting and improve recycling processes by detecting and classifying waste materials in images using YOLOv8. The categories targeted include plastic, glass, aluminum, and HDEP (High-Density Polyethylene).

Using advanced object detection algorithms, the model was trained on a dataset of annotated images and validated on 1001 images containing 1037 objects.

![image](https://github.com/user-attachments/assets/b1eac0b7-0114-4528-b592-b58fedbf559c)


These results indicate that the model is effective at detecting waste objects, particularly plastic and glass, while further improvement is needed for aluminum detection.

![image](https://github.com/user-attachments/assets/562b9bfa-9488-4bb1-a610-7d598d650582)


Script :

train.py

yolo task=detect mode=train model=yolov8n.pt data=dataset/data.yaml epochs=50 imgsz=640

validate.py

yolo task=detect mode=predict model=runs/detect/train/weights/best.pt source=path_to_image_or_folder

predict.py

yolo task=detect mode=predict model=runs/detect/train/weights/best.pt source=path_to_image_or_folder


3. Performance Metrics

![image](https://github.com/user-attachments/assets/f94a5449-deba-4ec3-8eef-3bd8c31f3f9b)

![image](https://github.com/user-attachments/assets/debd6db4-3b25-4b82-a736-59b18fddfd7f)


4. Installation and Usage

Installation

I had to download a database of waste such as cans, glass, plastic and HDPE already annotated or by annotating them on labeling so that the pretrained model of yoloV8 could train according to my requirements.

Training

Then you have to train the pre-trained model Yolov8 with train.py.

Validation

Then you have to evaluate the training model and observe the statistics of this training to see the conclusion of this training and see the potential evolutions.
With validate.py.

Inference

Finally, you have to do a concrete test with images to observe the proper functioning of the model.
With predict.py

5. References and Documentation

Papers and Frameworks

YOLOv8: https://docs.ultralytics.com
Dataset: Custom dataset, annotated for waste classification tasks.

Key Algorithms

YOLOv8: An anchor-free object detection model optimized for speed and accuracy.

6. Issues and Contributions

Known Issues

Aluminum objects have a low recall (62.2%), indicating some instances are missed.
Overlapping objects occasionally result in incorrect classifications.

Contributing

Report bugs or request features via GitHub Issues.
Submit pull requests with improvements or new features.
Contact for collaborations via GitHub.

7. Future Work

Expand the dataset to include more examples of aluminum and less common waste categories.
Deploy the model as a real-time application using edge devices for smart waste bins.
