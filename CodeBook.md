# Code Book

The script `run_analysis.R`performs the 5 steps described in the course project's definition.

* Files having the same number of columns and referring to the same entities are merged using the `rbind()` function.
* Then, only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* Descriptive variable names are given to all cols of the dataset.
* A new tidy dataset is created with the mean measures for each subject and activity type. The file is called `tidyData.txt`.

# Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std`, a numeric vector used to extract the desired data.
* `activities` similarly contains the correct names for the `y_data` dataset.
* `all_data` merges `x_data`, `y_data` and `subject_data` into a single dataset.
* `mean_data` contains the relevant averages which will be stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()'.
