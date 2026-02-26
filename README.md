# TIMIT-Speech-Recognition-using-Hidden-Markov-Models-HMM-

Overview
--------

This repository contains a Python implementation of an acoustic-phonetic speech recognition pipeline using a Gaussian Hidden Markov Model (HMM). The project focuses on extracting audio features from the DARPA TIMIT Continuous Speech dataset and decoding speech states using both the standard hmmlearn library and custom from-scratch implementations of fundamental HMM algorithms.

Key Features
------------

*   **Automated Dataset Retrieval**: Uses kagglehub to seamlessly download the DARPA TIMIT acoustic-phonetic continuous speech dataset.
    
*   **Audio Preprocessing**: Loads .wav files at a 16kHz sampling rate using librosa.
    
*   **Feature Extraction**: Computes 20-dimensional Mel-Frequency Cepstral Coefficients (MFCCs) with a hop length of 160 and applies z-score normalization (zero mean, unit variance) to the feature matrix.
    
*   **Gaussian HMM Training**: Fits an 8-state Gaussian HMM with diagonal covariance using hmmlearn.
    
*   **Custom Algorithm Implementations**:
    
    *   **Log-Emission Probabilities**: A custom function to compute multivariate Gaussian log-densities utilizing Mahalanobis distance.
        
    *   **The Forward Algorithm**: Computes the log-likelihood of the observation sequence dynamically using logsumexp for numerical stability.
        
    *   **The Viterbi Algorithm**: A dynamic programming approach to find the most probable sequence of hidden states (the Viterbi path) complete with backpointers.
        
*   **Algorithmic Validation**: Automatically compares the scores and decoded paths from the custom implementations against the robust hmmlearn library to ensure mathematical correctness.
    

Requirements
------------

Ensure you have Python 3 installed. You can install the required dependencies using pip:

pip install numpy librosa soundfile kagglehub matplotlib seaborn hmmlearn scipy   

Usage
-----

1.  Clone the repository and navigate to the project directory.
    
2.  Run the provided Jupyter Notebook (Sama.ipynb).
    
3.  The notebook will automatically:
    
    *   Download the TIMIT dataset.
        
    *   Search for the first available .wav file in the dataset directory.
        
    *   Extract and normalize MFCC features.
        
    *   Train the Gaussian HMM.
        
    *   Run and validate the custom Forward and Viterbi decoding passes.
