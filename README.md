# fall_detection
The model generator
## Data Source
 - [MobiAct](https://bmi.hmu.gr/the-mobifall-and-mobiact-datasets-2/) - this model uses the 2nd Release of MobiAct dataset 
## Description
### [feature_extraction]: Give set of features extracted from the MobiAct Dataset.
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
### [model_selection]: Compare the performance of RandomForestClassifier, LogisticRegression and rbf-SVC with tuned parameters.
### [real_model]: Train the model that is going to be integrated with the oli App.
## Dependencies
