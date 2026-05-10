# Master Info

## Questions

- Training:
  - Should the model be trained on just "normal" data, or should it also be trained on anomalous data (with the correct labels)?

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
- The window length should be fixed. For all the different domains...

## Roadmap

### Find more models

Currently I was looking for statistical methods like PCA or KMeans. Those methods do not need any training before inference. They will be "trained" directly on the data and find anomalies based on just that data. This can be problematic if for example the whole data is anomalous (i.e. sensor for ecg is upside down). Then the model will not be able to find any anomalies. So now I will look for models that need training.

#### Semisupervised models

- Left_STAMPi
- SAND
- MCD
- Sub_MCD
- OCSVM
- Sub_OCSVM
- AutoEncoder
- CNN
- LSTMAD
- TranAD
- USAD
- OmniAnomaly
- PatchTST
- AnomalyTransformer
- TimesNet
- FITS
- Donut
- OFA
- MOMENT_FT
- M2N2
- TSPulse_FT
- xLSTMAD

| Model                | TSB-AD-U VUS-PR || -------------------- | --------------: |
| `TSPulse_FT`         |            0.55 |
| `xLSTMAD`            |            0.40 |
| `MOMENT_FT`          |            0.39 |
| `USAD`               |            0.36 |
| `SAND`               |            0.34 |
| `CNN`                |            0.34 |
| `LSTMAD`             |            0.33 |
| `OmniAnomaly`        |            0.29 |
| `AutoEncoder`        |            0.26 |
| `TimesNet`           |            0.26 |
| `TranAD`             |            0.26 |
| `FITS`               |            0.26 |
| `OFA`                |            0.24 |
| `MCD`                |            0.24 |
| `OCSVM`              |            0.23 |
| `Donut`              |            0.20 |
| `AnomalyTransformer` |            0.12 |

**Pretraied Models in the TSB-AD-U leaderboard**
| Model          | TSB-AD-U score |
| -------------- | -------------: |
| `TSPulse (FT)` |           0.55 |
| `Time-RCD`     |           0.52 |
| `CHARM`        |           0.50 |
| `TSPulse (ZS)` |           0.48 |
| `MOMENT (FT)`  |           0.39 |
| `MOMENT (ZS)`  |           0.38 |
| `TimesFM`      |           0.30 |
| `Lag-Llama`    |           0.27 |
| `Chronos`      |           0.27 |
| `OFA`          |           0.24 |


### Test on more datasets

Still only use the datasets in the TSB-AD repository. Currently I only tested on the TODS dataset which contained sin
waves with synthetic anomalies. Now I need to test on more datasets, that also are generated from the BI-Vital sensor, like ECG data or Acceleration data. All those datasets should still be **univariate**!
