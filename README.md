# Making a Glass Detector App (or Any Object Detection App)

Your images does not have to be glasses, they can be anything like cars, keys, or fruits. Just make sure that you have enough data for training (100-200 images for each class of objects) 

## Training the TFLite Model

I divided the training code into three Colab Notebooks to make the steps easier to follow:
  1. get_model.ipynb: Run this code to download the SSD Mobilenet V2 COCO Model (You will need the model.ckpt and pipeline.config files for training) 
  2. custom_train.ipynb: Run this code to train the object detection model. You need the following things: 
      * model.ckpt (does not necessarily have to be the model.ckpt-0, it can be model.ckpt-50000 and so forth)
      * pipeline.config
      * 2 tfrecords files (one containing labeled training images and the other containing labeled test images)
      * label_map.pbtxt
      * If you do not know how to get tfrecords file and label_map.pbtxt file, check out this [tutorial](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/training.html#preparing-the-dataset) or [Tony607's tutorial](https://github.com/Tony607/object_detection_demo). 
      * Download the latest model.ckpt file after training for as many steps as you wish. 
  3. export-tflite.ipynb: Run this code to convert the model.ckpt and pipeline.config files into a tflite format (you will need the model.tflite file for the app) 

## Creating the App

Follow the steps in the Object Detection Android Demo to create the app. Create the app bundle and publish the app on Google Play. 

## Helpful Resources 

Most of the training code came from [Tony607](https://github.com/Tony607/object_detection_demo) under the MIT License. 
I made the android app using the [Object Detection Android Demo](https://github.com/tensorflow/examples/tree/master/lite/examples/object_detection/android) under the Apache 2.0 License. 
