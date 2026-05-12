OCR and information extraction system for scanned receipts using PaddleOCR and the SROIE 2019 dataset. Implemented text detection, recognition, preprocessing, annotation parsing, and evaluation using CER/WER metrics. Applied computer vision and NLP techniques for automated receipt understanding and structured data extraction.
🚀 Features
Receipt OCR pipeline using PaddleOCR
Automatic text detection and recognition
Rotated text handling using angle classification
Annotation parsing for SROIE dataset
OCR performance evaluation metrics
Bounding box visualization on receipts
Structured information extraction from receipts
Modular and reusable notebook workflow
🛠 Technologies Used
Python
PaddleOCR
PaddlePaddle
OpenCV
NumPy
Pandas
Matplotlib
PIL
JiWER
Kaggle Notebook Environment
📂 Dataset

The project uses the SROIE 2019 (Scanned Receipt OCR and Information Extraction) dataset from ICDAR.

Dataset contains:

Receipt images
Text bounding box annotations
Ground truth transcriptions
Key information labels
📊 Evaluation Metrics

The OCR system was evaluated using:

Character Error Rate (CER)
Word Error Rate (WER)
Precision
Recall
F1-score
🧠 Workflow
Load and preprocess receipt images
Parse annotation files
Visualize text bounding boxes
Run PaddleOCR detection and recognition
Compare predictions with ground truth labels
Calculate OCR evaluation metrics
Extract structured receipt information
📌 Project Goals
Build a robust OCR pipeline for scanned receipts
Improve recognition accuracy on noisy and rotated text
Automate business document digitization
Explore intelligent document understanding techniques

