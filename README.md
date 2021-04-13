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

# About the project

The Notebook file "DogsvsCats_vgg16_finetuned.ipynb" implements fine-tuning on VGG16 model. We want to use VGG16 to classify images of cats and dogs. Therefore, there are only two classes. Since the model is already trained on ImageNet to classify cats and dogs, all the layers in the model are freezed and only the last layer is retrained to classify only two classes. The resulting fine-tuned VGG16 model is saved as a h5 file. Later this fine-tuned model will be used to classify images of cats and dogs through a Flask web application. 

The Notebook file "classification-vgg16-finetuned-backend-flask-singleImage.ipynb" contains the codes for implementing the Flask web service which receives a single image from the user through a HTTP request, calls the fine-tuned VGG16 model, does a prediction on the image and returns the result back to the user.

The Notebook file "classification-vgg16-finetuned-frontend-flask-singleImage.ipynb" contains the JavaScript and HTML codes for a web application where the user can upload an image of a cat or a dog and send it to the Flask web service.

# Future work

As a further improvement to this project, the user can send a batch of images through the web application and on the web service side, the fine-tuned VGG16 model receives a batch of images and implements predictions on the batch.
