This code implements a **convolutional neural network (CNN)** for image classification, utilizing the fuctions available in the **TensorFlow and Keras libraries** for model development, training, and evaluation. The use of these libraries was choosen due to their ease of use and popularity. 

The dataset used has **10 classes** and can be found at the following link - https://www.kaggle.com/datasets/karimabdulnabi/fruit-classification10-class

It worth noting that in this particular run, the train and validation set provided from the dataset where merged in order to provide more flexibility when it comes to subdividing the data into training, validation and test set.  

The dataset is loaded using TensorFlow’s image_dataset_from_directory function, which **automatically labels the images based on their folder structure**. The data is batched for efficiency, and a few sample images along with their labels are visualized to confirm correct loading.

The images are **preprocessed by normalizing their pixel values to a range between 0 and 1**, ensuring that all features are on a consistent scale. Labels are converted to one-hot encoded vectors, suitable for multi-class classification. The dataset is then split into training (70%), validation (20%), and testing (10%) subsets.

The CNN model is constructed using a **sequential approach**. It comprises convolutional layers for feature extraction, pooling layers to reduce spatial dimensions, and dropout layers to prevent overfitting by randomly deactivating neurons during training. A flattening layer converts 2D feature maps into a 1D vector, followed by dense layers for classification. The final output layer uses a softmax activation function to produce probabilities for each of the ten classes.

The model is compiled with the **Adam optimizer** for adaptive learning rates, categorical crossentropy as the loss function for multi-class classification, and accuracy as the evaluation metric. **Early stopping** is implemented to halt training if validation loss does not improve for 10 consecutive epochs, preventing unnecessary computation and overfitting.

Training is carried out on the training set, with validation data used to monitor performance during each epoch. The script visualizes the training and validation loss and **accuracy curves** to analyze the training process and detect potential **overfitting or underfitting**.

After training, the model is evaluated on the test set to compute the final test loss and accuracy. Predictions are generated for the test set, and a classification report is displayed to summarize precision, recall, and F1-scores for each class. A confusion matrix is visualized to provide insights into class-wise performance and potential misclassifications.

**Main Points Covered:** 

-CNN
-TensorFlow and Keras libraries
-Multiclass
-Normalization
-Layer Structure
-Adam Optimizer
-Accuracy Curves
-Overfitting
