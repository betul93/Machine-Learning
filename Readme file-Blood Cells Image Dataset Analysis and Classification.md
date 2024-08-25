<a name="br1"></a> 

**Blood Cells Image Dataset Analysis and**

**Classification**

**Dataset**

The dataset used is the **Blood Cells Image Dataset** obtained from Kaggle. It contains images

of blood cells categorized into 8 classes.

**Downloading the Dataset**

To download the dataset, follow these steps:

1\. Install the Kaggle API.

2\. Upload your Kaggle API key (kaggle.json).

3\. Download the dataset using the Kaggle API command

!kaggle datasets download -d unclesamulus/blood-cells-image-dataset

**Extracting the Dataset**

Extract the dataset using the following command:

!unzip blood-cells-image-dataset.zip -d ./blood-cells-image-dataset

**Model Creation and Training**

**Data Preprocessing**

Images are preprocessed and augmented using TensorFlow's ImageDataGenerator:

·

·

·

Rescaled to a range of [0, 1]

Applied shear range and zoom range

Horizontal flip for additional augmentation

**Model Architecture**

A convolutional neural network (CNN) is used for classification:

·

·

·

·

Input layer followed by multiple convolutional and max-pooling layers

Flatten layer to prepare for dense layers

Fully connected dense layers with ReLU activation

Output layer with softmax activation for multiclass classification

**Training**

The model is compiled with:



<a name="br2"></a> 

·

·

·

Optimizer: Adam

Loss function: Categorical Crossentropy

Metrics: Accuracy

Trained for 3 epochs on augmented data batches from the dataset.

**Model Evaluation**

**Predictions**

Predictions are made using the trained model on the test dataset:

·

·

Batch-wise predictions obtained

Converted predictions to class labels using argmax

**Decision Tree Model**

A decision tree classifier is trained using the predictions of the deep learning model:

·

·

Used to analyze the performance of the CNN predictions

Accuracy measured using sklearn's accuracy\_score

**Saving and Loading the Model**

**Saving the Model**

The trained CNN model is saved as blood\_cell\_model.h5.

**Loading the Model**

The saved model (blood\_cell\_model.h5) is loaded for making predictions.

**Results and Reports**

**Decision Tree Model Accuracy**

The decision tree classifier's accuracy on predictions made by the CNN model is reported.

**Classification Report**

A detailed classification report is generated using classification\_report from sklearn,

showcasing precision, recall, F1-score, and support for each class.


