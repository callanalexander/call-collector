# Call Clustering

This repository demonstrates a post-processing pipeline after classification of bird vocalisations. The aim of this pipeline is to annotate individual notes for the target species (in this case, we use _Ninox strenua_, the Powerful Owl). This is achieved by segmenting the audio outputs and extracting acoustic features and then iteratively clustering those features using UMAP and HDBSCAN.

This is the associated code for the paper Alexander, C., Clemens, R., Roe, P., & Fuller, S. Automated Note Annotation after Bioacoustic Classification: Unsupervised Clustering of Extracted Acoustic Features Improves Detection of a Cryptic Owl. Available at SSRN 5099945.

The pipeline can be used with the outputs of any birdsong detection/SED model (e.g. BirdNET or Perch), all it requires is short .wav file snippets to work. However in this case we demonstrate it with a simple binary classifier to show how the process can also be used to identify false-positives and also facilitate semi-supervised learning. 

Please note we are currently updating the repo and some functionality may be limited, full code will be available by time of publication

# **Call Cluster - Birdsong Classification and Clustering**

This repository contains two Jupyter notebooks designed for analyzing and classifying birdsong using deep learning and clustering techniques.

- **`binaryclassifier.ipynb`** → A deep learning-based classifier for detecting owl vocalizations from spectrograms.
- GENERATE SPECTROGRAMS FOR TRAINING
This notebook trains a basic binary audio classifier (in this case, to classify owl vocalizations).
We suggest using your own data. You will need a folder of 5-second .wav file snippets that:
Do contain your target vocalization (positive examples)
Do not contain your target vocalization (negative examples)
Organize these files into 'positive' and 'negative' subfolders.

An example training dataset can be downloaded here: [INSERT LINK]
We also provide test models in the 'models' folder, and our field condition test dataset 
can be downloaded here: [INSERT LINK]

This notebook implements a binary classifier for detecting Powerful Owl calls in audio recordings. The pipeline includes:

1. Converting audio files to mel-spectrograms
2. Splitting data into training and test sets
3. Training a MobileNetV2-based model
4. Model evaluation
5. Inference on long audio recordings

- **`cluster_inspector.ipynb`** → A clustering and visualization tool for analyzing detected calls and separating true owl vocalizations from false positives.

---

## **Setup Instructions (For Anaconda and Beginners)**

### **Step 1: Download and Install Anaconda**
If you don’t have Anaconda installed, **download and install it here**:  
[Download Anaconda](https://www.anaconda.com/products/distribution)

---

### **Step 2: Download the Repository**
#### **Option 1: Using Git**
If you have Git installed, you can clone the repository using:

```bash
git clone https://github.com/YOUR-USERNAME/call_cluster.git
```

Then navigate into the folder:

```bash
cd call_cluster
```

#### **Option 2: Manually Download the Files**
If you **don’t** have Git installed:
1. Go to [GitHub Repository](https://github.com/YOUR-USERNAME/call_cluster).
2. Click the green **“Code”** button → **“Download ZIP”**.
3. Extract the ZIP file on your computer.

---

### **Step 3: Open Anaconda Prompt**
- **Windows:** Search for “Anaconda Prompt” in the Start Menu and open it.  
- **Mac:** Open Terminal and type `conda` to check if Anaconda is installed.

---

### **Step 4: Navigate to the Project Folder**
Once you’ve downloaded or cloned the repository, move into the project folder:

```bash
cd path/to/call_cluster
```

For example, if you extracted it into your **Documents** folder:

```bash
cd C:\Users\YourName\Documents\call_cluster
```

---

### **Step 5: Create a New Conda Environment**
Now, create a new environment called `call_cluster`:

```bash
conda create -n call_cluster python=3.8
```

Then **activate the environment**:

```bash
conda activate call_cluster
```

---

### **Step 6: Install Required Packages**
#### **Option 1: Install Everything from `requirements.txt`**
If you've downloaded the `requirements.txt` file, install all dependencies by running:

```bash
pip install -r requirements.txt
```

💡 **How to Find `requirements.txt`?**  
It is located **inside the project folder** (`call_cluster/`). If you’re unsure, check by running:

```bash
dir   # On Windows
ls    # On Mac
```

This should list the files, and you should see `requirements.txt`. If not, **make sure you're in the correct folder**.

#### **Option 2: Manually Install Packages**
If `requirements.txt` isn't working, install packages individually:

```bash
conda install tensorflow scikit-learn pandas numpy matplotlib pillow librosa soundfile sounddevice
pip install umap-learn hdbscan scikit-maad
```

---

### **Step 7: Install `tkinter` (For `cluster_inspector.ipynb`)**
`tkinter` is used in `cluster_inspector.ipynb` for UI elements.

- **Windows/macOS users:** `tkinter` is included with Python, so no extra steps.

If you **still get an error** when running `cluster_inspector.ipynb`, try installing it inside your conda environment:

```bash
conda install -c conda-forge tk
```

---

### **Step 8: Run the Jupyter Notebooks**
Start Jupyter Notebook by running:

```bash
jupyter notebook
```

Then:
- Open **`binaryclassifier.ipynb`** to run the deep learning classifier.
- Open **`cluster_inspector.ipynb`** to analyze and visualize clusters.

---

