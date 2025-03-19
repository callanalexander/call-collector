# Call Clustering

This repository demonstrates a post-processing pipeline after classification of bird vocalisations. The aim of this pipeline is to annotate individual notes for the target species (in this case, we use _Ninox strenua_, the Powerful Owl). This is achieved by segmenting the audio outputs and extracting acoustic features and then iteratively clustering those features using UMAP and HDBSCAN.

This is the associated code for the paper Alexander, C., Clemens, R., Roe, P., & Fuller, S. Automated Note Annotation after Bioacoustic Classification: Unsupervised Clustering of Extracted Acoustic Features Improves Detection of a Cryptic Owl. Available at SSRN 5099945.

Example training, prediction data and the test datasets used in the paper are available to download [Here](https://drive.google.com/drive/folders/1c9U5I7wh6b2DB_7faFlGx-AR0fpF5vW5?usp=drive_link), there is also a link in the supplementary materials with an outline of each folder. 

The pipeline can be used with the outputs of any birdsong detection/SED model (e.g. BirdNET or Perch), all it requires is short .wav file snippets to work. However in this case we demonstrate it with a simple binary classifier to show how the process can also be used to identify false-positives and also facilitate semi-supervised learning. 

Please note this is a draft version of the repository which we are currently updating with a full tutorial and test data. Primary code is currently available but full code and test files will be available upon publication


