# Tree detection from satellite images

This application users can be join the group and talk each other.

## Introduction

The use of satellite imagery for detection has become increasingly important for a wide variety of applications. Tree detection is one of the important applications of detecting from satellite images. Some important areas of tree detection from satellite images are the correct information about distribution of forest areas for forest management, forest research and similar areas.
In this project, a dataset was prepared by labelling trees in some regions of Turkey with Python's library LabelImg. Then, the object detection algorithm, one of the machine learning techniques, was used. Roboflow and YOLOv5 Object Detection Model were used during Object detection.

## Methods

 - Obtaining Satellite Images: Satellite images were taken from the cities of Antalya, Mersin, Bursa and Malatya from Turkey using Google Earth. In the acquisition of satellite images, the altitude from the sea was determined as 266 meters. The images were recorded in 8K resolution from the Google Earth Pro application in order to have the highest resolution of the satellite images received.

![This is an image](/images/antalya.png.jpg)

 - Dataset Labelling: LabelImg was used to label the acquired satellite images. Since the trees will be detected via YOLOv5, the recording format was chosen as YOLO and the dataset was saved with a .txt format.
During tagging, consideration was given to situations such as overlapping trees and the shadow of the trees, and tagging was done accordingly.


![This is an image](/images/antalya_labeled.png)


 - Model: The YOLO algorithm was used with the Roboflow tool [7]. The YOLO algorithm is important because of its speed, high accuracy, and learning capabilities. We used the YOLOv5 model. YOLOv5 is based on the PyTorch framework, which has a larger community than YOLOv4-Darknet. Detection was performed in Google Colab environment.
 - Data Analytics and Visualization: TensorBoard used for modelling data.  
 - Implementation: First of all, the prepared dataset was uploaded to Roboflow. A version was created for this with Roboflow. Roboflow also has created an API key for this dataset. This API Key is compatible with Roboflow, after making changes to some parts of the YOLOv5 Google Colab notebook, we performed the detection process.

## Results and Discussion

We visualise our model using TensorBoard. Precision measure shows how much of the bbox predictions are correct. Our range is generally between 0.5 and 0.9. During detection, we set the confidence threshold as 0.7. And we were able to detect all the trees we wanted with a confidence threshold above 0.7.


![This is an image](/images/precision_result_tenserboard.png)


Below graph shows bounding box regression loss (Mean Squared Error).


![This is an image](/images/bounding_box_regression_loss.png)


During our detection, we obtained the trees of the Antalya region satellite image (Fig 1.) with 100% correct results. However, since we adjusted our dataset to detect discrete trees for this semester, we did not fully detect overlapping trees in Mersin. With this, we achieved 100% success for split trees. Next semester, we will work on these situations and detect tree types.


![This is an image](/images/detection_from_antalya.png)



![This is an image](/images/detection_from_mersin.png)


