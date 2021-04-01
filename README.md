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

<p align="center">
 <img src = "https://github.com/SDP-Group-1/fall_detection/blob/main/image/SMV_formula.svg"
</p>
 
The Signal Magnitude Vector (SMV for short) is calculated by the formula above, which is actually the norm of the composition of 3-axes acceleration.

<p align="center">
 <img src = "https://github.com/SDP-Group-1/fall_detection/blob/main/image/3-axes.png"
</p>

We segmented the readings' record into 5s window, the figure below is the smv curve of the window in which a typical fall event happened. From the figure, we can see for a typical fall event there would be a peak form curve of the SMV, and after the peak the man/woman who has just experienced a fall would lie on the ground naturally and stay motionless.

<p align="center">
 <img src = "https://github.com/SDP-Group-1/fall_detection/blob/main/image/fall_event.png"
</p>

**mean_smv** is the mean value of SMVs during the window period.

**std_smv** is the standard deviation of SMVs during the window period.

**std_mless** is the standard deviation of the motionless stage. We determine the motionless stage by wether it is after the minimum value of SMV.

**max_smv** is the maximum of SMV during the window period.

**min_smv** is the minimum of SMV during the window period.

**slope** is the slope of the straight line between the point that the SMV reaches its maximum and the point SMV reaches its minimum, and it can be calulated by：

<p align="center">
 <img src = "https://github.com/SDP-Group-1/fall_detection/blob/main/image/SL_formula.svg"
</p>

**duration** is the number of recording frames between the maximum SMV and minimum SMV.

[model_selection](https://github.com/SDP-Group-1/fall_detection/blob/main/model_selection.ipynb): Compare the performance of RandomForestClassifier, LogisticRegression and rbf-SVC with different combinations of hyperparameters.

The frame of this program allows to do trials on more classifiers with different settings.

[model_export](https://github.com/SDP-Group-1/fall_detection/blob/main/model_export): Train the model that is going to be integrated with the oli App and export it as a pickle file.

## Dependency
```sh
python=3.8.0
scikit-learn=0.24.1
numpy=1.19.2
pandas=1.2.2
```

## Reference

[1] Casilari, E., Santoyo-Ramón, J., &amp; Cano-García, J. (2017). Analysis of public datasets for wearable fall detection systems. Sensors, 17(7), 1513. doi:10.3390/s17071513

[2] Vavoulas, G., Chatzaki, C., Malliotakis, T., Pediaditis, M., &amp; Tsiknakis, M. (2016). The mobiact DATASET: Recognition of activities of daily living using smartphones. Proceedings of the International Conference on Information and Communication Technologies for Ageing Well and E-Health. doi:10.5220/0005792401430151

[3] Sucerquia, A., López, J., &amp; Vargas-Bonilla, J. (2017). SisFall: A fall and MOVEMENT DATASET. Sensors, 17(12), 198. doi:10.3390/s17010198

[4] Ge, Y., &amp; Xu, B. (2014). Detecting falls using accelerometers by adaptive thresholds in mobile devices. Journal of Computers, 9(7). doi:10.4304/jcp.9.7.1553-1559

[5] He, J., Zhang, Z., Wang, X., &amp; Yang, S. (2019). A low power fall sensing technology based on fd-cnn. IEEE Sensors Journal, 19(13), 5110-5118. doi:10.1109/jsen.2019.2903482

[6] Shi, Y., Shi, Y., &amp; Wang, X. (2012). Fall detection on mobile phones using features from a five-phase model. 2012 9th International Conference on Ubiquitous Intelligence and Computing and 9th International Conference on Autonomic and Trusted Computing. doi:10.1109/uic-atc.2012.100
