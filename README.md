# LeafC
Training data is based on 200 images each of Pongamia pinnata, Jatropha, Chinar, Mango and Alstonia scholaris.

here is a brief overview of what has been done in the project:

Setup and Dependencies: The project starts by installing necessary libraries, primarily scikit-learn and pillow-heif. pillow-heif is registered as an opener to handle HEIF image formats. Feature Extraction: Several functions are defined and used to process leaf images. These functions perform: Image Segmentation: Isolating the leaf from the background. Morphological Feature Calculation: Extracting features like area, perimeter, aspect ratio, and circularity from the segmented leaf shape. Texture Feature Calculation: Computing texture properties like contrast, correlation, and energy using Gray-Level Co-occurrence Matrix (GLCM). Data Processing: The code processes a dataset of leaf images organized into class folders. It extracts the defined features for each image and organizes them by class. This data is then converted into a pandas DataFrame and saved to a CSV file (classifier_features.csv). One-Class SVM Classification: A One-Class SVM model is trained for each leaf type. A sample leaf image is then checked against these models to determine if it belongs to any of the known classes. Multi-Class SVM Classification: A Multi-Class SVM model is trained on the extracted features and their corresponding leaf type labels. This model is used for the final classification of a leaf image that was initially identified as 'known' by the One-Class SVMs. The performance of this multi-class model is evaluated using accuracy and a classification report. In essence, the project aims to classify leaf images by extracting features from the images and using a two-step SVM approach: first checking if the leaf is of a known type using One-Class SVMs, and then classifying it into a specific type using a Multi-Class SVM if it is known.

1. The first code block helps extract data from the .zip file
2. The second code block helps distinguish between the known five and the unknown sample and classify it into its respective class.
3. The third code block splits the training data 80-20 into training and test data sets and evaluates the model.

The 5 folders -  Jatropha, Alstonia, Chinar, Mango and Pongamia - comprise the training data set 
The 2 folders titled known (new images of Mango leaves for test) and unknown (unidentified species) are the test data for use by the examiner. 

How to run the code?
- The base path is common to all five dataset folders
- We copy the base path and the path of the image chosen
- The user inputs the data to run the code
