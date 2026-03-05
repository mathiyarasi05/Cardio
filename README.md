# Cardio
It's about diagnosing cardiovascular diseases by using ECG and Echocardiography
Multimodal Cardiac Analysis Framework
ECG Classification + ECHO Segmentation
1. ECG – Heartbeat Classification
Dataset
• MIT-BIH Arrhythmia Dataset
• PTB Diagnostic ECG Dataset
• Source: Kaggle (Heartbeat Dataset by shayanfazeli)
Model Architecture
The ECG classification model is a 1D Convolutional Neural Network consisting of three Conv1D blocks (32, 64, 128 filters), Batch Normalization, MaxPooling layers, Fully Connected layers (128 and 64 units), Dropout (0.3), and a Softmax output layer with 5 classes.
Optimizer: Adam
Loss: Sparse Categorical Crossentropy
Metric: Accuracy
Required Packages (ECG)
pip install tensorflow pandas numpy scikit-learn kaggle
Procedure to Run ECG Code
1. Mount Google Drive in Colab.
2. Install Kaggle API.
3. Upload kaggle.json and configure API.
4. Download dataset using Kaggle command.
5. Unzip dataset.
6. Run preprocessing, training (10 epochs), and evaluation.
2. ECHO – Cardiac Image Segmentation
Dataset
• CAMUS Human Heart Dataset
• Source: Kaggle (camus-human-heart-data by shoybhasan)
Model Architecture – Attention U-Net
The ECHO segmentation model uses an Attention U-Net architecture with encoder-decoder structure and attention gates in skip connections. It performs multi-class segmentation (4 classes: Background, LV Cavity, LV Myocardium, Left Atrium).
Optimizer: Adam (learning rate = 1e-4)
Loss: Categorical Crossentropy
Metrics: Accuracy, Dice Score, IoU, HD95, ASD
Required Packages (ECHO)
pip install tensorflow numpy opencv-python matplotlib nibabel SimpleITK scikit-image scipy scikit-learn kaggle
Procedure to Run ECHO Code
1. Install Kaggle API.
2. Configure kaggle.json.
3. Download CAMUS dataset.
4. Unzip dataset.
5. Run preprocessing (.nii.gz to PNG with normalization and SRAD filtering).
6. Train Attention U-Net (50 epochs, batch size 8).
7. Save model (.h5) and evaluate using medical segmentation metrics.
Evaluation Metrics
• Dice Score (DSC)
• Intersection over Union (IoU)
• Hausdorff Distance (HD95)
• Average Surface Distance (ASD)
