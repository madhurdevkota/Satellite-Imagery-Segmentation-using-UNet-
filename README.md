# Satellite-Imagery-Segmentation-using-UNet


#### 1. Introduction and Project Overview
This project involves the use of the U-Net architecture for segmenting satellite images to classify various geographical features such as water, roads, and vegetation. The project utilizes deep learning techniques to process and analyze high-resolution images from Dubai, aiming to identify and differentiate between several land cover types.

#### 2. Data Acquisition and Preparation
##### 2.1 Image and Label Acquisition
The dataset consists of satellite imagery and corresponding labels stored in separate directories. Images are in JPEG format while labels are in PNG format, each indicating different geographical features.
##### 2.2 Preprocessing Steps
###### Scaling and Resizing
Images are resized to a uniform size (256x256 pixels) and scaled using Min-Max normalization to ensure the model receives inputs within a normalized range. Labels are similarly resized and converted from BGR to RGB format.
###### Reclassification of Labels
Labels are mapped from hex color codes to categorical labels representing different geographical features. This transformation is crucial for training the segmentation model.

#### 3. Deep Learning Preparation
##### 3.1 Data Preparation for Neural Network
Images and labels are converted into NumPy arrays for processing with the neural network. Labels are one-hot encoded to match the expected format of the neural network.
##### 3.2 Training and Test Split
The dataset is split into training and test sets, maintaining a proportion that ensures adequate data for learning while allowing for robust model evaluation.

#### 4. Model Development
##### 4.1 U-Net Architecture
The U-Net model is constructed with several convolutional and max-pooling layers to capture spatial hierarchies and features. The architecture includes dropout layers to prevent overfitting and Conv2DTranspose layers for upsampling to match the output dimensions with the input dimensions.
##### 4.2 Model Compilation
The model uses a composite loss function combining Dice loss and categorical focal loss to handle class imbalance effectively. Accuracy and the Jaccard index are used as performance metrics.

#### 5. Model Training and Evaluation
##### 5.1 Training the Model
The model is trained using batches, with callbacks for early stopping based on accuracy and the Jaccard index to prevent overtraining.
##### 5.2 Model Evaluation
The trained model is evaluated using the test set, and performance metrics such as loss, accuracy, and the Jaccard index are plotted to assess the model's effectiveness.

#### 6. Results Visualization and Interpretation
##### 6.1 Visualizing Predictions
The output from the model is visualized to compare predicted labels against true labels, providing a visual assessment of the model's accuracy in segmenting and classifying different geographical features.
##### 6.2 Observing Layer Activations
Activations in various layers of the U-Net model are visualized to understand which features are most activated by different geographical inputs, giving insights into what the network learns at different stages.

---
