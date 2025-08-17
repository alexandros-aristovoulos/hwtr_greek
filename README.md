# Hand Written Text Recognition (for Greek)

A detailed video explaining the enire process <b>in Greek</b> can be found [here](https://www.youtube.com/watch?v=0wiOQFia3xI&ab_channel=AlexandrosAristovoulos) 

### Description
This is part of my master thesis titled "Recognition Of Handwritten Text With The Use Of Machine Learning" (Original tiltle in Greek: "Αναγνώριση Χειρόγραφου Κειμένου Με Χρήση Μηχανικής Μάθησης") for the University of Patras.

The code in this repository reflects my thought process for finding an optimal neural network. My first attempt was to train a [neural network for English](https://github.com/alexandros-aristovoulos/hwtr_english) and i used everything I learnt to train this one. For the Greek model I had to create the dataset myself, with hadwritten samples collected from students at the university of Patras. As a result this model has a limited vocabulary and it is more of a proof of concept. The words are all areas in Athens. The reason for this was that the model could be used to automate the grouping and routing of packages in the city. 

The final neural network that has the following characteristics: <br>

<u>**Input layer**</u> <br>
- 2D convolutional layer 
    - 48 nodes
- Max pooling function
    - size 3x3

<u>**Hidden layers**</u> <br>
- 3 2D convolutional layers
- 48 nodes each
- 0.20 dropout

<u>**Output layer**</u> <br>
- Fully connected layer
- 30 nodes (equal to the word dictionary)
- 0.20 dropout

<u>**Training properties**</u>
- 8 batch size
- Early stopping with 6 step patience
- restore best weights

This model can be found and tested inside the folder: `iteration2`


### Getting started
1. Install the dependencies from the [Dependencies section](#dependencies)

2. Create the Dataset from the scanned images <br>
    - In order to create the dataset you have to run [create_dataset.ipynbfrom](https://github.com/alexandros-aristovoulos/hwtr_greek/blob/master/create_dataset.ipynb)
    - You can change the percentages for the training, validation and test dataset by editing the `split_dataset(paths)` function. Default is 70% training, 15% validation and test.

  
### Folder structure
- Every `iteration` is trying to determine a strategy that will improve the validation accuracy of the hwtr model
    
- The `iterations2` folder used the best models from the first iteration and retrained them. The idea was that the models could have reached a "local maximum efficiency" and by retraining them thez could reach their maximum potential. 


### Dependencies
- [Tensorflow](https://www.tensorflow.org/install/pip) <br>
Create and train the neural network

- [Numpy](https://numpy.org/install/) <br>
Perform calculations with arrays, load and read arrays from .npy files

- [OpenCV](https://pypi.org/project/opencv-python/) <br>
Display images and read their pixel values as arrays 

- [Matplotlib](https://pypi.org/project/matplotlib/) <br>
Display images
