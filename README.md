# fall_detection
The model generator
## Data Source
 - [MobiAct](https://bmi.hmu.gr/the-mobifall-and-mobiact-datasets-2/) - this model uses the 2nd Release of MobiAct dataset 
## Description
### [feature_extraction]: Give set of features extracted from the MobiAct Dataset.
The current version takes 19 features into consideration, the table below includes 12 features which are simple statistics on the raw sensor readings:
        <table>
   <tr>
      <td>Name</td>
      <td>Description</td>
   </tr>
   <tr>
      <td>mean_ax</td>
      <td>Mean of x-axis acceleration</td>
   </tr>
   <tr>
      <td>mean_ay</td>
      <td>Mean of y-axis acceleration</td>
   </tr>
   <tr>
      <td>mean_az</td>
      <td>Mean of z-axis acceleration</td>
   </tr>
   <tr>
      <td>mean_gx</td>
      <td>Mean of x-axis gyroscope</td>
   </tr>
   <tr>
      <td>mean_gy</td>
      <td>Mean of y-axis gyroscope</td>
   </tr>
   <tr>
      <td>mean_gz</td>
      <td>Mean of z-axis gyroscope</td>
   </tr>
   <tr>
      <td>std_ax</td>
      <td>Standard deviation of x-axis acceleration</td>
   </tr>
   <tr>
      <td>std_ay</td>
      <td>Standard deviation of y-axis acceleration</td>
   </tr>
   <tr>
      <td>std_az</td>
      <td>Standard deviation of z-axis acceleration</td>
   </tr>
   <tr>
      <td>std_gx</td>
      <td>Standard deviation of x-axis angular velocity</td>
   </tr>
   <tr>
      <td>std_gy</td>
      <td>Standard deviation of y-axis angular velocity</td>
   </tr>
   <tr>
      <td>std_gz</td>
      <td>Standard deviation of z-axis angular velocity</td>
   </tr>
</table>
### [model_selection]: Compare the performance of RandomForestClassifier, LogisticRegression and rbf-SVC with tuned parameters.
### [real_model]: Train the model that is going to be integrated with the oli App.
## Dependencies
