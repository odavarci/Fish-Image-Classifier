# Fish-Image-Classifier

### 1) Create Dataset
  - We have worked on the dataset on Kaggle (https://www.kaggle.com/datasets/crowww/a-large-scale-fish-dataset) which contains thousand image per class, nine class in total.
  - Firstly, I have saved the path of each folder contains images.
  - Then, I have created a custom dataset class. This class takes a list of paths to folders, gets the path of each individual image, enumerates the labels and converts images in order the transformation method I passed.
  - Finally, I have created a dataset object with custom class and split dataset into train and test sets with 0.8 ratio since it is the ratio that mostly used.

### 2) Train an ANN Model
  - To achive a satisfying result, I have tried multiple model with different parameters.
    
      Number of Layer: I have started to train a model with one hidden layer only to see if a simple model could give good enough performance to solve the problem to prevent spending much more time to train more complex models. As a result one hidden layered model could not exceed 0.50-0.55 ratio of test success rate and two hidden layered model achieved 0.75 ratio of success rate. 4 hidden layered model just gave satisfying results which is 0.95 ratio of success.

      Number of Neuron: After deciding number of layers of model, I started to experiment on number of neurons for every layer. Again, I have started to experiment with less neuron to get faster results. I have tried 128-64-32-16, 512-256-64-32 and 1024-512-128-64 combinations.

      Dropout Ratio: Since 0.5 ratio of dropout is commonly used, I have not tried to optimize this parameter.

      Optimizer: I have used Adam optimizer with 0.001 learning rete and not needed to optimize this parameter too.
  
  - After defining a model class each time, I have trained the model for 10 epoch. At this point, greater number epoch may gave better results but to not make train duration any longer, I decided to not try longer sessions of training.
  - While training, I have saved train and test accuracy and loss every epoch to visualize changes during time to understand whether overfitting occured or not. To prevent overfitting, I have used batch normalization and dropout mechanisms.
  - After saving the model that result 0.9483 accuracy on test dataset, I have completed the development part of the project.


Kaggle Notebook: https://www.kaggle.com/code/merdavarc/notebook5942a62d7e
