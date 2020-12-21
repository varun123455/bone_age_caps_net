Project ID: PW20AK05


Project Type : Research


Project Title: Pediatric Bone Age Detection


Team Members: Siddharth Kailasam(01FB16ECS153) , Varun Manjunath(01FB16ECS434) , Iresh Hiremath(01FB16ECS141)


Project Guide: Dr Anant Koppar


Project Abstract:

The aim of this project is to predict the estimated bone age of an individual in the age range of 1-228 months. This project deploys a neural network known as capsule network
to perform the task of predicting the bone age of the individual based on the X-ray image of his wrist bone. The input to the model is an X-ray image of the left palm which are the
input features along with the bone age in months which are the output features the model has to learn. The capsule network is an improvement of a neural network which is widely
used in state of art for image processing known as Convolution Neural Network (CNN). A CNN treats the pixel’s of an image as mere numbers where each filter produces a
single intensity value in a capsule network each filter produces a vector when applied on the set of pixels. Hence this aspect of treating images as a set of vector’s makes it rotation
invariant even with relatively lesser training samples. This network overcomes the same shortcomings. One of the major needs of this project is that the manual method of
observing the bone age can make it time consuming and more prone to human error and bias. However, this network can help overcome those shortcomings.

Some files need a cloud to execute and cannot execute on an ordinary laptop. It has been tried and tested on google cloud.

Code Execution :

Connect to google cloud through SSH jupyter lab :-
Download gcloud. Link for Ubuntu - https://cloud.google.com/sdk/docs/downloads-apt-get
Type the following commands -
$ gcloud init
$ gcloud compute ssh <vm-name> -- -L 8080:localhost:8080
Open localhost:8080 on your browser

Execute preprocess-show.py :-
This folder is a demo of the preprocessing steps involved given a test image.
This folder could be run locally
Execution - 
Create a folder named 'data-show'
execute the given command -
$ python preprocess-show.py <path/to/the/test/image>
The preprocessing steps will be present in the folder 'data-show'

Execute main_preprocess.py using preprocess.py -
main_preprocess.py is used to preprocess all images from the source to the destination.
It can execute on a normal machine.
Execution -
create a folder named 'data2'
execute the given command -
$ python main_preprocess.py <path/to/source/folder> <path/to/destination/folder> 
The output now lies in the destination folder

To execute train.ipynb -
This file is used to train the neural network using preprocessed image
It cannot be executed on a normal system and needs to be executed on a cloud.
Execution -
Upload the file to your google cloud account
Upload the preprocessed training images in the directory named 'preprocess' in the same google cloud directory where this file is present
Put the expected output for the given image name in a file named 'boneage-training-dataset.csv' in the same google cloud directory where this file is present
Run all cells
Training checkpoints are automatically created

To execute create_csv.ipynb -
This file is used to create a CSV which compares the deviation of actual with predicted for every image in a directory.
It cannot be executed on a normal system and needs to be executed on a cloud.
Execution -
Upload the file to your google cloud account
Upload the preprocessed training images in the directory named 'preprocess' in the same google cloud directory where this file is present
Put the expected output for the given image name in a file named 'boneage-training-dataset.csv' in the same google cloud directory where this file is present
Put the checkpoint created by the file 'train.ipynb' in the same google cloud directory this file is present
Run all cells
The CSV file is automatically created

To execute main.py -
The main.py is used to run the GUI and predict the network. 
It cannot be executed on a normal system and needs to be executed on a cloud.
Execution -
open a new terminal on google cloud
go to the directory where main.py is present
type the following command -
$ python main.py
Go to your local terminal and type the following -
$ gcloud compute ssh <vm-name> -- -L 5000:localhost:5000
Open localhost:5000 on browser
