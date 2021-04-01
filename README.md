# fall_detection
The model generator
## Data Source
 - [MobiAct](https://bmi.hmu.gr/the-mobifall-and-mobiact-datasets-2/) - this model uses the 2nd Release of MobiAct dataset 
## Description
 - [feature_extraction]: Give set of features extracted from the MobiAct Dataset.
     The current version takes 19 features into consideration:
        | Name        | Description    |
        | --------   | -----:   |
        | 香蕉        | $1      | 
        | 苹果        | $1      |
        | 草莓        | $1      |
 - [model_selection]: Compare the performance of RandomForestClassifier, LogisticRegression and rbf-SVC with tuned parameters.
 - [real_model]: Train the model that is going to be integrated with the oli App.
