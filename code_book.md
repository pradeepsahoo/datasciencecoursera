The code book for assignment/project work related to  "Getting and Cleaning Data"

For the  data set, the measurements we  calculate will need to be described in more detail than someone will sneak into 
the spreadsheet/csv data set. This code book contains  information:

Information about the variables (including units!) in the data set not contained in the tidy data
Information about the summary choices was made
Information about the experimental study design used

Data source

This dataset is derived from the "Human Activity Recognition Using Smartphones Data Set" which was originally 
made avaiable here: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The attached R script (run_analysis.R) performs the following to clean up the data:

1. Merges the training and test sets to create one data set, namely
train/X_train.txt with test/X_test.txt -- the result is a 10299 x 561 data frame, as in the original description 
("Number of Instances: 10299" and "Number of Attributes: 561")

train/subject_train.txt with test/subject_test.txt -- the result is a 10299 x 1 data frame with subject IDs,

train/y_train.txt with test/y_test.txt -- the result is also a 10299 x 1 data frame with activity IDs.

2. Reads file features.txt and extracts only the measurements on the mean and standard deviation for each measurement.
The result is a 10299 x 66 data frame, because only 66 out of 561 attributes are measurements on the mean and standard 
deviation. All measurements appear to be floating point numbers in the range (-1, 1).

3. Reads activity_labels.txt and applies descriptive activity names to name the activities in the data set:

LAYING
SITTING
STANDING
WALKING
WALKING_DOWNSTAIRES
WALKING_UPSTAIRES


4. The script also appropriately labels the data set with descriptive names: all feature names (attributes) and 
activity names are converted to lower case, underscores and brackets () are removed.
Then it merges the 10299x66 data frame containing features with 10299x1 data frames containing activity labels and 
subject IDs.

The result is saved as result.txt, a 10299x68 data frame such that the first column contains
activity name, the second column subject id and the last several columns are measurements. 
Subject IDs are integers between 1 and 30 inclusive. Names of the attributes are similar to the following:

tbodyacc-mean-x

tbodyacc-mean-y

tbodyacc-mean-z

tbodyacc-std-x

tbodyacc-std-y

tbodyacc-std-z

tgravityacc-mean-x

tgravityacc-mean-y

5. Save data write.csv(averages, file='assignment/result1.txt', row.names=FALSE)
It is 180x68 because there are 30 subjects and 6 activities, thus "for each activity and each subject" means 30*6=180 rows. 
Note that the provided R script has no assumptions on numbers of records, only on locations of files.

Thank you.
