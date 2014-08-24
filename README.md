datasciencecoursera
===================
Data Science Coursera Repository

Data Science track — The homework/project for "Getting and Cleaning Data Course Project"

The purpose of this project is to demonstrate  ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. This peer graded project work will be required to submit: 
1) a tidy data set as described below, 
2) a link to a Github repository with your script for performing the analysis, and 
3) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. 

You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.  

Project work background:
One of the most exciting areas in all of data science right now is wearable computing - see for example this article . Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained: 

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

Here are the data for the project: 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

A R script called run_analysis.R that does as below. 

1.Merges the training and the test sets to create one data set.

2.Extracts only the measurements on the mean and standard deviation for each measurement. 

3.Uses descriptive activity names to name the activities in the data set

4.Appropriately labels the data set with descriptive variable names. 

5.Creates a second, independent tidy data set with the average of each variable for each activity and each subject.

The project work approach is as follows:

0. Download the dataset if not present. downloaed File=./getdata-projectfiles-UCI HAR Dataset.zip
1. rbind two data files to fullfill requirement #1 above.
2. Take only std() and mean() features, subset the dataset, thus fulfilling requirement 2; the result is in mean_and_std
3. Load the activity labels, and replace indices with names. The approach used was adopted from internet search link http://stackoverflow.com/questions/22475400/r-replace-values-in-data-frame-using-lookup-table That completes this req #3
4. Combines the labels and the data set using cbind; doing that for both mean_and_std and X. That closes req #4.
5. Using the X, calculating an aggregate using mean for averaging, averaging over activity and subject; then save the result to a file thus closing req #5

Thanks
