# dsc-phase-4-project-Image-Classification-with-Deep-Learning
Student name: Qilun Chen<br>
Student pace: full time<br>
Scheduled project review date/time: May/13/2022<br>
Instructor name: Praveen Gowtham<br>
# Purpose
Identifying whether or not they have pneumonia by Image-Based Deep Learning. Pneumonia is lungs with inflammatory, blackage of the bronchiole, and Alveoli with fluid. When interpreting the x-ray, the radiologist will look for white spots in the lungs (called infiltrates) that identify an infection.
# Gather the Data
This dataset contains thousands of validated Chest X-Ray images  described. The images are split into a training set and a testing set of independent patients. Images are labeled as (disease)-(randomized patient ID)-(image number by this patient) and split into 2 directories: Pneumonia, and NORMAL. The dataset is from Mendeley Data. University of California San Diego, Guangzhou Women and Children's Medical Center. The three contributors are Daniel Kermany, Kang Zhang, Michael Goldbaum.
# Data pre-processing
By checking around 10 x-ray images from dataset, the lungs are on the middle images. Therefore, I did not rotate the model or any pre-processing on the data.
# EDA
first, to generate a ImageDataGenerator and rescales to 1/255. Second, resized each images to 150x150, set batch size to 20. The class mode is binary. 
# Modeling
Generate a sequential model, and add layers. The final layer should be sigmoid, because i solving yes or no question. Compile the model by using RMSprop optimizer. Fit the model with train generator with 100 steps 30 epochs. Than I get model accuracy 86%
# Optimize and Strategize
We see that our accuracy on our test data is 86.5%. This may indicate overfitting. Our recall is greater than our precision, indicating that almost all pneumonia images are correctly identified but some normal images are falsely identified. We should aim to increase our precision. To do that, I needs more data or another examination like CT findings
