# fall_detection
The model generator
## Data Source
 - [MobiAct](https://bmi.hmu.gr/the-mobifall-and-mobiact-datasets-2/) - this model uses the 2nd Release of MobiAct dataset 
## Description
[feature_extraction](https://github.com/SDP-Group-1/fall_detection/blob/main/feature_extraction.ipynb): Give set of features extracted from the MobiAct Dataset.

The current version takes 19 features into consideration, the table below includes 12 features which are simple statistics on the raw sensor readings:

| Name |	Description |
| ---- | ----------- |
| mean_ax |	Mean of x-axis acceleration |
| mean_ay	| Mean of y-axis acceleration |
| mean_az	| Mean of z-axis acceleration |
| mean_gx	| Mean of x-axis gyroscope |
| mean_gy	| Mean of y-axis gyroscope |
| mean_gz	| Mean of z-axis gyroscope |
| std_ax	| Standard deviation of x-axis acceleration |
| std_ay	| Standard deviation of y-axis acceleration |
| std_az	| Standard deviation of z-axis acceleration |
| std_gx	| Standard deviation of x-axis angular velocity |
| std_gy	| Standard deviation of y-axis angular velocity |
| std_gz	| Standard deviation of z-axis angular velocity |

The other 7 features are respectively **mean_smv**, **std_smv**, **std_mless**, **max_smv**, **min_smv**, **slope**, **duration**.

![image](https://github.com/SDP-Group-1/fall_detection/blob/main/image/SMV_formula.svg)

The Signal Magnitude Vector (SMV for short) is calculated by the formula above, which is actually the norm of the composition of 3-axis acceleration.

![image](https://github.com/SDP-Group-1/fall_detection/blob/main/image/3-axis.png)

We segmented the readings' record into 5s window, the figure below is the smv curve of the window in which a typical fall event happened. From the figure, we can see for a typical fall event there would be a peak form curve of the SMV, and after the peak the man/woman who has just experienced a fall would lie on the ground naturally and stay motionless.

![image](https://github.com/SDP-Group-1/fall_detection/blob/main/image/fall_events.png)

**mean_smv** is the mean value of SMVs during the window period.
**std_smv** is the standard deviation of SMVs during the window period.
**std_mless** is the standard deviation of the motionless stage. We determine the motionless stage by wether it is after the minimum value of SMV.
**max_smv** is the maximum of SMV during the window period.
**min_smv** is the minimum of SMV during the window period.
**slope** is calculated by ![image](https://github.com/SDP-Group-1/fall_detection/blob/main/image/SL_formula.svg)

[model_selection](https://github.com/SDP-Group-1/fall_detection/blob/main/model_selection.ipynb): Compare the performance of RandomForestClassifier, LogisticRegression and rbf-SVC with different combinations of hyperparameters.

[model_export](https://github.com/SDP-Group-1/fall_detection/blob/main/model_export): Train the model that is going to be integrated with the oli App and export it.
## Dependencies
