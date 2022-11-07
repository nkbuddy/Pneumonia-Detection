# project-Image-Classification-with-Deep-Learning
Student name: Qilun Chen<br>
Student pace: full time<br>
Scheduled project review date/time: May/13/2022<br>
Instructor name: Praveen Gowtham<br>

# Purpose
Identifying whether or not they have pneumonia by Image-Based Deep Learning. Pneumonia is lungs with inflammatory, blackage of the bronchiole, and Alveoli with fluid. When interpreting the x-ray, the radiologist will look for white spots in the lungs (called infiltrates) that identify an infection.

# Technology in this project
It includes numpy, pandas, tensorflow, matplotlib, sklearn, keras, and seaborn

# Gather the Data
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/number_of_images.png?raw=true)<br>
This dataset contains thousands of validated Chest X-Ray images  described. The images are split into a training set and a testing set of independent patients. Images are labeled as (disease)-(randomized patient ID)-(image number by this patient) and split into 2 directories: Pneumonia, and NORMAL. The dataset is from Mendeley Data. University of California San Diego, Guangzhou Women and Children's Medical Center. The three contributors are Daniel Kermany, Kang Zhang, Michael Goldbaum.
# Data pre-processing
By checking around 10 x-ray images from dataset, the lungs are on the middle images. Therefore, I did not rotate the model or any pre-processing on the data.
# EDA
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/load_data.png?raw=true)<br>
first, to generate a ImageDataGenerator and rescales to 1/255. Second, resized each images to 150x150, set batch size to 3. The class mode is binary. 
# Modeling
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/layers.png?raw=true)<br>
Architecture of Multi-Layer Perceptron used: input->[conv2D->maxpool2D] x 4 -> Flatten -> Dense -> Sigmoid<br>
Generate a sequential model, and add layers. The final layer should be sigmoid, because i solving yes or no question. Compile the model by using RMSprop optimizer. Fit the model with train generator with 100 steps 30 epochs. Than I get model accuracy 86%
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/feature_map.png?raw=true)<br>
This is the model's feature map.
# Model Performance
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/first_model.png?raw=true)<br>
The training accuracy and training loss approach climax in 10 epoch. But validation accuracy and validation loss are unstable.<br>
<br>
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/confusion_matrix.png?raw=true)<br>
In 500 images, There are 317 true postive, 113 true negative, 1 false postive, 69 false negative.
# Example
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/TruePostive.png?raw=true)<br>
True Postive images<br>
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/TrueNegative.png?raw=true)<br>
True Negative images<br>
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/FalsePostive.png?raw=true)<br>
False Postive images<br>
![alt text](https://github.com/nkbuddy/Pneumonia-Detection/blob/main/images%20for%20github/FalseNegative.png?raw=true)<br>
False Negative images<br>
# Optimize and Strategize
We see that our accuracy on our test data is 86.5%. This may indicate overfitting. Our recall is greater than our precision, indicating that almost all pneumonia images are correctly identified but some normal images are falsely identified. We should aim to increase our precision. To do that, I needs more data or another examination like CT findings
