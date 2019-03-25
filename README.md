
# MyNet-Classification
Cancer Dataset

1. The Dataset : 
- Contains 4188 images from a medical research of Cancer tumors.
- The dataset has images belonging to three classes - "Benign" "Malignant" and "Background".


2. Network Architecture :

5 convolutional layers with convolutional filters for feature extraction, MaxPooling and Batch Normalization are used with "RELU"  activation function.

- Max Pooling is a sample-based discretization process. The objective is to down-sample an input representation, reducing its
  dimensionality and allowing for assumptions to be made about features contained in the sub-regions binned.
- Batch Normalization is performed on the data to speed up the process of learning by normalizing the features hence reducing covariance
  shift.
- There are 4 Dense layers for forward propagation which are in series with the convolutional layers.
- Dropout regularization is added to avoid overfitting.
- The output layer then generates the output using "SoftMax" activation function.

  
3. Data Augmentation :

Data Augmentation methods help us improve our training accuracy. We use the Keras ImageDataGenerator library to increase the number of data points in a dataset by performing rescaling, rotating figures along horizontal & vertical axes, changing the width, height, shear and zoom of the images. 

Keras Class to Generate batches of tensor image data with real-time data augmentation. The data will be looped over (in batches).     

    datagen_train = ImageDataGenerator(rescale=1./255,rotation_range=40,width_shift_range=0.2,height_shift_range=0                                                              shear_range=0.2,zoom_range=0.2,horizontal_flip=True,fill_mode='nearest')


4. Adam Optimizer :

Adam is an optimization algorithm that can be used instead of the classical stochastic gradient descent procedure to update network weights iterative based in training data. Specifically, the algorithm calculates an exponential moving average of the gradient and the squared gradient, and its parameters control the decay rates of these moving averages. 

5. Training :

The model is then trained by fitting the training data. Using 50 Epochs and 60 steps per Epoch by calculating the loss and accuracy at every step thus giving our final performance accuracy. The Accuracy and Loss curves of Training and Validation Datasets are then plotted. 
