# TODO for Master Thesis preparation
Information mainly gatherd from paper *The Elephant in the Room: Towards A Reliable Time-Series Anomaly Detection Benchmark* (https://proceedings.neurips.cc/paper_files/paper/2024/file/c3f3c690b7a99fba16d0efd35cb83b2c-Paper-Datasets_and_Benchmarks_Track.pdf)

Test the following methods (mentioned in the paper: https://proceedings.neurips.cc/paper_files/paper/2024/file/c3f3c690b7a99fba16d0efd35cb83b2c-Paper-Datasets_and_Benchmarks_Track.pdf) on the univariate dataset:
- [ ] Sub-PCA
- [ ] KShapeAD
- [ ] Series2Graph (Requires licence)
- [ ] KMeansAD

Evaluation Metrics:
Point-wise:
- AUC-ROC
- AUC-PR
- Standard-F1
- PA-F1
Range-wise:
- R-based-F1
- Affiliation-F1
- VUS-ROC
- VUS-PR
- PATE

Questions:
- should we test the methods on the whole dataset? Seems very big. Maybe start with a couple datasets.
  - => For now, just use the TODS datast. It is a synthetic dataset with sin curves.
- How do these methods perform on different types of datasets / outlier types?
  - Select a few different datasets with unique
- What's the difference between 