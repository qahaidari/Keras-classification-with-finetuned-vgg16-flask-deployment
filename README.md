# Keras-classification-with-finetuned-vgg16-flask-deployment
Implementation of a classification neural network in TensorFlow/Keras by fine-tuning VGG16 model and its deployment to Flask web service

# About VGG16 neural network model
[VGG16](https://arxiv.org/abs/1409.1556) is a deep convolutional neural network (CNN) which was trained on a subset of [ImageNet](http://www.image-net.org/) dataset and achieves a 92.7% test accuracy; [VGG16 for Classification and Detection](https://neurohive.io/en/popular-networks/vgg16/). The input images to VGG16 network are of size 224x224 RGB. Below shows the architecure of VGG16 model.

![architecture of VGG16 model](https://github.com/qahaidari/Keras-classification-with-finetuned-vgg16-flask-deployment/blob/main/vgg16-neural-network.jpg)

# About ImageNet dataset
ImageNet is a dataset with over 14 million images from roughly 22000 different classes. VGG16 neural network was trained on around 1.2 million training images consisting of 1000 image classes with 1000 images in each class, 50,000 validation images, and 150,000 testing images. All the images in ImageNet have a fixed resolution of 256x256 [VGG16 for Classification and Detection](https://neurohive.io/en/popular-networks/vgg16/).

# About Flask
Flask is a Python framework that makes building web applications easy. Here, Flask is used to implement a frontend web application where the user can enter data (such as images for classification) and send them to a backend server. The backend server is also implemented by Flask which receives the user input data through HTTP methods, processes and returns a response to the frontend application. In this project, the response would be a prediction on if the input image is a cat or a dog. Since in this project, the web application and web service are implemented on Google Colab, flask-ngrok should be installed according to [this tutorial](https://medium.com/@kshitijvijay271199/flask-on-google-colab-f6525986797b). Below command is used to do so.

!pip install flask-ngrok
