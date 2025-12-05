1. CVE-VulDetect: BiLSTM-Transformer Architecture with CVE-Centric Hybrid Labeling for Vulnerability Detection in IoT Software
Authors

Aabia Ather
SEECS, NUST, Islamabad, Pakistan
aather.msit25seecs@seecs.edu.pk

Maheen Arshad
SEECS, NUST, Islamabad, Pakistan
marshad.msit25seecs@seecs.edu.pk

Mahnoor Azhar
SEECS, NUST, Islamabad, Pakistan
mazhar.msit25seecs@seecs.edu.pk


2. Project Overview

This project implements a BiLSTM-Transformer hybrid architecture for detecting vulnerabilities in IoT software.
A CVE-centric hybrid labeling method is integrated to improve dataset quality and model performance by combining static analysis indicators with CVE-based vulnerability records.

The repository contains the notebook and code used for model training, evaluation, and dataset processing.

  How to Run the Code

1. Open Google Colab
Create a new notebook for running the framework.

2. Enable GPU support
Go to:
Runtime → Change runtime type → Hardware accelerator → GPU

3. Mount Google Drive
Run the following in a Colab cell:

from google.colab import drive
drive.mount('/content/drive')


4. Organize your project files
Make sure the project folder is stored in Drive at:

/content/drive/MyDrive/CVE-VulDetect/

Inside this folder, include:

data/ (preprocessed IoT code samples)
models/
preprocessing/
labeling_pipeline.py
train.py
evaluate.py
requirements.txt

5. Install required Python packages
Run:

pip install -r /content/drive/MyDrive/CVE-VulDetect/requirements.txt

or manually:

pip install numpy pandas scikit-learn torch transformers matplotlib


6. Import the project code
Add your project folder to the Python path:

import sys
sys.path.append('/content/drive/MyDrive/CVE-VulDetect')


7. Run the hybrid CVE labeling pipeline (optional)
This step refines labels using static tools + CVE validation:

!python /content/drive/MyDrive/CVE-VulDetect/labeling_pipeline.py


8. Train the BiLSTM + VulBERTa model
Execute:

!python /content/drive/MyDrive/CVE-VulDetect/train.py --model bilstm_vulberta


9. Evaluate the trained model
After training:

!python /content/drive/MyDrive/CVE-VulDetect/evaluate.py


10. View performance metrics
The notebook will display:

Accuracy
Precision, Recall, F1-score
Comparison between LSTM, BiLSTM, Transformer models
Effect of CVE validation on performance
