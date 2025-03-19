# Call Clustering

This repository demonstrates a post-processing pipeline after classification of bird vocalisations. The aim of this pipeline is to annotate individual notes for the target species (in this case, we use _Ninox strenua_, the Powerful Owl). This is achieved by segmenting the audio outputs and extracting acoustic features and then iteratively clustering those features using UMAP and HDBSCAN.

This is the associated code for the paper Alexander, C., Clemens, R., Roe, P., & Fuller, S. Automated Note Annotation after Bioacoustic Classification: Unsupervised Clustering of Extracted Acoustic Features Improves Detection of a Cryptic Owl. Available at SSRN 5099945.

The pipeline can be used with the outputs of any birdsong detection/SED model (e.g. BirdNET or Perch), all it requires is short .wav file snippets to work. However in this case we demonstrate it with a simple binary classifier to show how the process can also be used to identify false-positives and also facilitate semi-supervised learning. 

Please note we are currently updating the repo and some functionality may be limited, full code and test files will be available upon publication


