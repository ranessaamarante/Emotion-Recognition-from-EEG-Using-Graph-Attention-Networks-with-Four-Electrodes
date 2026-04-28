# Emotion Recognition from EEG Using Graph Attention Networks with Four Electrodes

EEG-based emotion classification using a Graph Attention Network (GAT) with four electrodes (FT7, FT8, P7, P8) on the SEED dataset. Evaluated under Leave-One-Subject-Out (LOSO), achieving 94.85% mean accuracy across 15 subjects.

## Dataset

Download the SEED dataset at https://bcmi.sjtu.edu.cn/home/seed/seed.html

## Directory Structure

SEED_EEG/
├── Preprocessed_EEG/
│   ├── label.mat
│   ├── 1_20131027.mat
│   └── ...
├── organizing_and_padding_dataset.ipynb
├── extracting_DE_features.ipynb
└── model.ipynb


## How to Run

Run the notebooks **in order**:

1. **`organizing_and_padding_dataset.ipynb`** — organizes `.mat` files into HDF5 and pads all trials to 48,000 samples. Outputs `padded_EEG.h5`.
2. **`extracting_DE_features.ipynb`** — extracts differential entropy features per channel, window, and frequency band. Outputs `EEG_DE_data.h5`. 
3. **`model.ipynb`** — builds graphs, trains the GAT under LOSO, and reports accuracy per subject.
