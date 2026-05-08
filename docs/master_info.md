# Master Info

## Goal of this master thesis

The goal is to find a statistical or machine learning model that is able to detect anomalies in the data.

The data is coming from the [BI-Vital](https://bivital.eu/) sensor of Bielefeld University. This means that the data
contains multiple domains (e.g. ECG, Acceleration, Gyro). All of those sub-data streams are univariate, so one
dimensional.

## Constraints

- There should exist only one model which detects anomalies on all those different domains.
- The model should use parameters, meaning it should be trainable. Some statistical methods don't need training.
- The model should also be light weight. This is not the hightest priority, but the model should run on the BI-Vital
device. Maybe at the end of this work we will test it. For now that is not the priority though.

## Roadmap

### Find more models

Currently I was looking for statistical methods like PCA or KMeans. Those methods do not need any training before inference. They will be "trained" directly on the data and find anomalies based on just that data. This can be problematic if for example the whole data is anomalous (i.e. sensor for ecg is upside down). Then the model will not be able to find any anomalies. So now I will look for models that need training.

### Test on more datasets

Still only use the datasets in the TSB-AD repository. Currently I only tested on the TODS dataset which contained sin
waves with synthetic anomalies. Now I need to test on more datasets, that also are generated from the BI-Vital sensor, like ECG data or Acceleration data. All those datasets should still be **univariate**!
