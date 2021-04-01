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

The other 7 features are respectively mean_smv, std_smv, std_mless, max_smv, min_smv, slope, duration.
<a href="https://www.codecogs.com/eqnedit.php?latex=SMV&space;=&space;\sqrt{A_{x}^2&space;&plus;&space;A_{y}^2&space;&plus;&space;A_{z}^2}" target="_blank"><img 

[model_selection](https://github.com/SDP-Group-1/fall_detection/blob/main/model_selection.ipynb): Compare the performance of RandomForestClassifier, LogisticRegression and rbf-SVC with different combinations of hyperparameters.

[model_export](https://github.com/SDP-Group-1/fall_detection/blob/main/model_export): Train the model that is going to be integrated with the oli App and export it.
## Dependencies
