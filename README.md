# TF Motif Prediction in TIGD3 Gene - IBIS Competition


Project Overview

This project was developed as part of the IBIS competition, focusing on predicting transcription factor (TF) motifs in the TIGD3 gene using various DNA sequence datasets. The approach combined data preprocessing, augmentation, and convolutional neural network (CNN) models to identify significant motifs that regulate gene expression. The project utilized datasets derived from PBM, SMS, and HTS methods, integrating sequence augmentation and innovative data processing techniques to enhance model performance.

Datasets

PBM Datasets: The project utilized QNZS-normalized and SD-preprocessed PBM data files to identify potential binding sites through z-score normalization and thresholding techniques.
HTS Dataset: Processed sequences extracted from FASTQ files with a quality control threshold to ensure high fidelity of nucleotide data.
SMS Dataset: This dataset was filtered out to improve model performance but was initially considered for comprehensive analysis.

Methods

Data Processing and Augmentation:

Normalization and labeling of sequence data based on statistical thresholds.
Data augmentation techniques including reverse complement, sequence shifting, and edge mutations were applied to increase the diversity of positive training examples.

Feature Extraction:

DNA sequences were encoded into k-mers of varying lengths, which were then integer-encoded to serve as inputs for the CNN model.
Custom padding and augmentation strategies were applied to balance sequence lengths and enhance model robustness.

Model Architecture:

A simplified CNN model with multiple convolutional layers and max-pooling was implemented to capture patterns within the sequences.
A custom Focal Loss function was used to address class imbalance during training, enhancing the model’s ability to detect minority class motifs.

Training and Evaluation:

Model training was conducted using augmented datasets with a detailed evaluation of performance metrics such as AUROC and AUPRC.
Confusion matrices were plotted to visualize prediction accuracy across epochs.
Prediction and Post-processing:

The model was evaluated on test sequences, with probability scores calibrated and adjusted to meet IBIS competition requirements.

## Results

- The model successfully identified significant TF motifs within the TIGD3 gene sequences, demonstrating strong performance metrics:
- AUPRC 0.59 (Area Under Precision-Recall Curve): Demonstrated high precision in identifying true motifs.
- AUROC 0.87 (Area Under Receiver Operating Characteristic Curve): Showcased the model’s ability to distinguish between motif and non-motif sequences.

How to Run the Project

## Clone the Repository:

- git clone https://github.com/yourusername/TFs-motif-discovery-in-TIGD3-gene.git
- cd TFs-motif-discovery-in-TIGD3-gene

Ensure you have Python installed along with the required libraries.

Prepare the Data.

Place the relevant PBM and FASTQ files in the data/ folder and update the paths in the code as needed.
Run the Training Script.
Run the Prediction Script.

File Descriptions

TFs_prediction_on_TIGD3_gene.ipynb: Main notebook containing the entire pipeline from data processing to model evaluation.
cnn_model.pth: Saved model weights for inference.
parsed_sequences.csv: Pre-processed test sequences for prediction.

## Future Work

- Extend the model to include additional TF motifs and sequence datasets.
- Explore other neural network architectures and loss functions to further enhance prediction accuracy.

Acknowledgments

This project was developed as part of the IBIS Challenge, AAA G2A discipline, focusing on TF motif prediction in TIGD3 gene sequences.
