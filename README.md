# Call Collector

This repository demonstrates a post-processing pipeline after classification of bird vocalisations. The aim of this pipeline is to annotate individual notes for the target species (in this case, we use _Ninox strenua_, the Powerful Owl). This is achieved by segmenting the audio outputs and extracting acoustic features and then iteratively clustering those features using UMAP and HDBSCAN.

This is the associated code for the paper Alexander, C., Clemens, R., Roe, P., & Fuller, S. Automated Note Annotation after Bioacoustic Classification: Unsupervised Clustering of Extracted Acoustic Features Improves Detection of a Cryptic Owl. Available at SSRN 5099945.

Example training, prediction data and the test datasets used in the paper are available to download [Here](https://drive.google.com/drive/folders/1c9U5I7wh6b2DB_7faFlGx-AR0fpF5vW5?usp=drive_link), there is also a link in the supplementary materials with an outline of each folder. 

The pipeline can be used with the outputs of any birdsong detection/SED model (e.g. BirdNET or Perch), all it requires is short .wav file snippets to work. However in this case we demonstrate it with a simple binary classifier to show how the process can also be used to identify false-positives and also facilitate semi-supervised learning. 

Please note this is a draft version of the repository which we are currently updating with a full tutorial and test data. Primary code is currently available but full code and test files will be available upon publication

## Overview

This repository contains a set of Jupyter notebooks that form an end-to-end workflow for processing audio recordings of owl calls:

1. Training a deep learning model to detect owl calls
2. Running the model on long-duration audio files to detect potential calls
3. Extracting audio snippets of potential calls
4. Analyzing and clustering the detected vocalizations to identify call types

## Notebooks

### 1. `train_model.ipynb`
- Generates spectrograms from audio snippets
- Creates train/test splits for model evaluation
- Trains a MobileNetV2-based neural network to classify owl calls

### 2. `test_and_run_model.ipynb`
- Evaluates model performance on test datasets
- Processes hour-long audio files to detect owl calls 
- Extracts audio snippets of detected calls for further analysis

### 3. `cluster_inspector.ipynb`
- Extracts acoustic features from detected calls using Regions of Interest (ROIs)
- Performs dimensionality reduction using t-SNE or UMAP
- Clusters similar call types using DBSCAN or HDBSCAN
- Provides an interactive GUI for inspecting and analyzing clusters

## Installation with Anaconda

This project uses several audio processing libraries. We recommend using Anaconda to manage dependencies.

### Step 1: Install Anaconda

Download and install Anaconda from [https://www.anaconda.com/download](https://www.anaconda.com/download)

### Step 2: Create a new environment and install dependencies

```bash
# Clone the repository
git clone https://github.com/yourusername/owl-call-detection.git
cd owl-call-detection

# Create and activate conda environment
conda create -n owl-detection python=3.8
conda activate owl-detection

# Install all dependencies from requirements.txt
pip install -r requirements.txt

# For GPU support (optional, if you have a compatible GPU)
pip install tensorflow-gpu
```

This will install all the necessary libraries including:
- NumPy, Pandas, Matplotlib for data manipulation and visualization
- TensorFlow for deep learning
- Librosa and Pydub for audio processing
- UMAP and HDBSCAN for dimensionality reduction and clustering
- MAAD (Multimodal Animal Acoustic Detector) for acoustic feature extraction

## Usage

1. Open Jupyter Notebook:
```bash
conda activate owl-detection
jupyter notebook
```

2. Follow the notebooks in sequence:
   - Start with `train_model.ipynb` to train your classifier
   - Use `test_and_run_model.ipynb` to process audio files
   - Analyze results with `cluster_inspector.ipynb`
```

## Customizing for Other Species

While this framework was developed for Powerful Owl calls, it can be adapted for other species by:

1. Training the detection model with examples of your target species
2. Adjusting spectrogram parameters to match your species' vocal range
3. Tuning clustering parameters to identify call types specific to your target species

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- This project utilises sci-kit maad for segmentation and feature extraction:
- Ulloa, J. S., Haupert, S., Latorre, J. F., Aubin, T., & Sueur, J. (2021). Scikit‐maad: An open‐source and modular toolbox for quantitative soundscape analysis in python. Methods in Ecology and Evolution, 12(12), 2334-2340.



