# MACHINE-LEARNING-BASED-DETECTION-OF-APPLICATION-LAYER-DDoS-ATTACK
An approach to predict the application layer DDoS attacks using Machine Learning .

Machine Learning model to detect DDoS attacks by identifying and distinguishing between traffic produced by freely accessible tools and legitimate traffic.

# Dataset Link
	https://drive.google.com/file/d/1hzJ8Gdx4yMwbIJlc3v-bloPVV3sPFhiN/view?usp=drive_link

# INTRODUCTION:
      ● A DDoS attack is a type of malicious attack in which an attacker floods the target application with traffic from numerous sources, making the application inaccessible for legitimate users.
      ● Attackers use botnets to send traffic to the application, making it appear as though the traffic originated from different sources. 
      ● There are different forms of DDoS attacks, Application-layer DDoS is one of them, in which the attacker targets the application layer of the victim and attempts to exhaust its resources, causing it to fail.
      ● The rise in DDoS attacks is attributed to the availability of freely accessible DDoS attack tools,which can be easily downloaded from the internet, enabling anyone to launch a DDoS attack effortlessly. 
      ● Our goal is to examine how the easy availability of such tools affects the frequency and intensity of DDoS attacks. 
      ● Additionally, we aim to investigate possible solutions for detecting and mitigating this threat.

# Steps Involved
1. DATASET
2. DATA PREPARATION
3. FEATURE SELECTION
4. DATA SCALING
5. CLASSIFIER

# DATASET
● This work makes use of the CICIDS2017 dataset, profiling the abstract behavior of 25 users based on email, FTP, SSH, HTTP, and HTTPS protocols.There were initially 692703 samples in the dataset.
● HeartBleed Attack samples are removed from the dataset,because HeartBleed Attack is not a DDoS Attack , leaving 692692 samples with 78 characteristics in the final dataset.
● Key properties and characteristics of the dataset:	
      1 Publicly available
			2 Realistic and diverse
			3 Large and complex
			4 Labeled

# DATA PREPARATION
● In this dataset, our data, with the exception of a few feature columns, was clean and ready to use.
● There are a total of 1008 nan values present inside the Flow Bytes/s feature.
● In addition, there are 289 infinite values present inside the Flow Bytes/s features.
● The nan and infinite values are substituted with the median and the maximum values of the feature column.
● In addition, there are 1297 infinite values present inside the Flow Packets/s features.

# FEATURE SELECTION
● In our work, we use DT for the purpose of feature selection.
● We populate all the data in the dataset to the DT then we consider the importance of features.
● we take the mean of feature importance of all features and use it as a threshold.
● Any feature with feature importance below the threshold is discarded.
● In the end of process, we are left with six features.
● It is worth to note that we hold all prime essential features in order to detect diverse and various DDoS attack toolkits.

# DATA SCALING
● This work uses the Min-Max Standard Scaler to transform the data into a number between the minimum and maximum values.

# CLASSIFIER
● Choosing the ideal number of neurons and layers in a MLP is an important step in building a neural network where several guidelines have been proposed in the literature.
● we use MLP to classify 4 DDoS attacks and benign traffic with 6 features only.
● The procedure begins with no hidden layers, and considers the accuracy, precision, recall, and F1 score as performance metrics.
● The number of hidden layers is subsequently increased incrementally, with the corresponding number of neurons determined through Gridsearch.

# EXPERIMENTS AND RESULTS
● After feature selection, the 6 selected features are populated to a MLP of three layers.
● The first hidden layer, second hidden layer and third hidden layer consists of 100,200 and 250 neurons, respectively
● Based on the evaluation, our model obtains a level of accuracy of 99%, precision of 96%, a level of F1 score of 97%, and recall of 98% with adam optimizer.
● There are a variety of optimizers to choose when developing ML methods. SGD, LBFGS, and Adam are three famous optimizers that are frequently used for MLPs.
● After precise experimentation, we have found that Adam optimizer/solver showed the best accuracy .
