# number-plate-recognition-project
Project Architecture. 

![image](https://github.com/willytsinda/number-plate-recognition-project/assets/97414552/7f1bfacc-e1b6-4bfc-8edc-a8fd96baecc4)

Steps defined:

Phase 1

- Image collection from different sources : 

Images should have a vehicle with a number/license plate

- Labelling each and every image manually:

Critical step i.e. whole project is dependent on this process

- Data Preprocessing:

Normalization, Transformation etc. 

With the clean data, a powerful Deep Learning Model is trained for object detection. This is for the detection/recognition of the number/license plate 

- After model training, it is stored in frozen format 

The above steps come in the labelling and training phase


Phase 2 

Below are the production steps of the deep learning model:

- Using Validation data i.e. data used to test, the same data preprocessing techniques that were applied to the data in the training phase are used

- In order to achieve object detection of the number/license plates of vehicles the model that was saved is restored and the validation images are passed to it i.e. make Object Detection according to the project architecture image shown above

- The above step returns the Region of Interest (RoI). 

This is the position of the number plate according to the image passed to the restored model


Phase 3

- Send RoI image to Optical Character Recognition (OCR) 

This is to be able to return the text from the image

In this project, Google Tesseract is the OCR 

- Pipeline the whole model built 


Phase 4

- A web application is created in Flask i.e., RESTful API 

- User uploads a vehicle image from the front-end 

- The back-end/server-side, model processes it and returns the vehicle number

