# iit-uptake-capstone

# Problem Objective
Unlabelled signal data was leveraged by using it to train Autoencoders in order to generate estimated features and use them to improve the performance of a supervised model trained with labels.

# Data Source 
The data being used by us in project is openly available at Backblaze . Backblaze data center daily collects snapshots of each operational drive. 

# Problem and Data Pipeline
The problem was that signal data is available of equipment but maintenance data is not. Hence we need to leverage the left unlabeled signal data to improve performance of supervised model classifier predicting failure of equipment. 

In our project, maintenance data is Failure column in drive data, and that is assumed to be limited for this objective. First Autoencoder is trained to over normal behaviour of operational drive data by dropping the rows with label of Failure(label 1). This data which only represents normal behaviour of drive is used to train Autoencoder. 

Then Supervised Classifier (Random Forest) is trained over features on other dataset to predict failure of drives. Actual features used in Supervised Classifier is then fed to trained Autoencoder to estimate features, calculate residuals by subtracting actual features and estimated features. Now, new dataset which contains actual features along with all the residuals is fed to Supervised Classifier and changes in its performance is observed. 

# Results 
Random Forest performance was improved with residuals as recall and precision is increased with model recognizing True alarms better and ignoring false ones. Moreover, the false negatives (missed alarms) were decreased which was very important as missed alarms will lead to monetary loss of client costing due to failure without an alarm.






