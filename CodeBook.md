---
# Variables
* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` are the variables that contain the data from the original data set.
* `x_data`, `y_data` and `subject_data` merge the variables mentioned previously to be used in analysis.
* `features` contains the labels for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`which is a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.

# Overview

The script `run_analysis.R`performs the functions described in the course project's definition.

* All the similar data is merged using the `rbind()` function. At the same time we address those files having the same number of columns and same number of factors.
* Then, only those columns with the mean and standard deviation measures are taken from the dataset. After we get those columns, we give them the correct labels that are taken from `features.txt`.
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* On the whole dataset, those columns with vague column names are corrected.
* Last but not least, we generate a new dataset with all the average measures for each subject and activity type. The output file is called `averages_data.txt.
