# Deep Learning-Based Respiratory Disease Classification Using Lung Sounds

A research project focused on developing deep learning approaches for **automated respiratory disease classification using lung sound recordings**. The project explores audio signal processing, time-frequency feature extraction, and deep learning architectures to investigate the recognition of respiratory diseases from stethoscope-recorded lung sounds.

The research aims to build a reproducible experimental framework for multi-class respiratory disease classification using publicly available datasets and modern deep learning techniques.

## Research Objectives

The primary objectives of this research are:

- Develop automated respiratory disease classification approaches using lung sound recordings.
- Transform raw respiratory audio signals into meaningful time-frequency representations.
- Investigate different deep learning architectures for respiratory sound classification.
- Evaluate the effects of optimizers, learning rates, batch sizes, and random seeds.
- Address class imbalance and improve minority-class recognition.
- Investigate model generalization using patient-independent data splitting.
- Compare model performance using comprehensive evaluation metrics.

## Target Disease Classification

The research focuses on eight respiratory health categories:

| No. | Disease | Full Form |
|---|---|---|
| 1 | COPD | Chronic Obstructive Pulmonary Disease |
| 2 | Asthma | Asthma |
| 3 | Pneumonia | Pneumonia |
| 4 | Bronchiectasis | Bronchiectasis |
| 5 | Bronchiolitis | Bronchiolitis |
| 6 | URTI | Upper Respiratory Tract Infection |
| 7 | LRTI | Lower Respiratory Tract Infection |
| 8 | Healthy | Healthy Control |

## Dataset

**ICBHI Respiratory Sound Database**

Dataset: [Respiratory Sound Database – Kaggle](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database)

The dataset contains respiratory sound recordings collected using digital stethoscopes, along with patient diagnosis information.

**Dataset characteristics:**
- WAV-format respiratory sound recordings
- Stethoscope-recorded lung sounds
- Patient-level diagnosis metadata
- Multiple respiratory disease categories
- Patient identification information

## Research Methodology

### 1. Audio Preprocessing

Raw lung sound recordings undergo preprocessing to ensure consistent input for deep learning models.

- Audio loading using Librosa
- Resampling to 16 kHz
- Fixed-duration audio segmentation
- Waveform normalization
- Handling corrupted or invalid recordings

### 2. Log-Mel Spectrogram Extraction

Log-Mel Spectrograms are used to convert one-dimensional respiratory audio signals into two-dimensional time-frequency representations.

| Parameter | Configuration |
|---|---|
| Sample Rate | 16,000 Hz |
| Audio Duration | 5 seconds |
| Mel Bands | 128 |
| FFT Size | 1024 |
| Hop Length | 256 |
| Minimum Frequency | 50 Hz |
| Maximum Frequency | 8,000 Hz |

These representations allow deep learning architectures to learn relevant respiratory sound patterns.

### 3. Patient-Independent Data Splitting

To minimize patient-level data leakage, recordings are divided based on unique patient IDs.

| Dataset | Percentage |
|---|---:|
| Training | 70% |
| Validation | 15% |
| Testing | 15% |

The same patient-level split will be maintained across comparative experiments to ensure a consistent evaluation protocol.

### 4. Deep Learning Architectures

The research investigates different deep learning architectures for respiratory disease classification using Log-Mel Spectrogram representations.

Potential architectures include:

- Basic Convolutional Neural Network (CNN)
- ResNet
- EfficientNet
- DenseNet
- MobileNet
- Convolutional Recurrent Neural Network (CRNN)
- Other suitable deep learning architectures

The architectures will be investigated and compared based on classification performance, computational complexity, and generalization ability.

### 5. Optimization and Hyperparameter Investigation

Different optimization algorithms and hyperparameter configurations will be investigated to understand their influence on model performance.

**Optimization algorithms:**
- Adam
- AdamW
- SGD
- RMSprop

**Experimental parameters:**

| Parameter | Configuration |
|---|---|
| Learning Rates | 0.001, 0.0001 |
| Batch Size | 32 |
| Maximum Epochs | 150 |
| Random Seeds | 42, 123, 2024, 7, 2025 |
| Early Stopping Patience | 15 |
| Loss Function | CrossEntropyLoss |

The experimental framework will support systematic comparisons across different architectures and optimization configurations.

### 6. Model Evaluation

The models will be evaluated using the following metrics:

- Accuracy
- Precision
- Recall
- Macro F1-Score
- Macro ROC-AUC
- Class-wise Precision, Recall, and F1-Score
- Confusion Matrix

Macro-averaged metrics will be emphasized because the dataset may contain substantial class imbalance.

### 7. Visualization and Experiment Tracking

The research will include visual analysis and systematic experiment logging.

- Training and validation loss curves
- Training and validation accuracy curves
- Confusion matrices
- Class distribution visualization
- ROC curves
- Model comparison plots
- Optimizer comparison plots
- CSV-based experiment tracking
- Model checkpoint saving

## Research Workflow

```text
Lung Sound Dataset
        |
        v
Audio Preprocessing
        |
        v
Log-Mel Spectrogram Extraction
        |
        v
Patient-Independent Data Splitting
        |
        v
Deep Learning Model Development
        |
        v
Model Training and Optimization
        |
        v
Validation and Hyperparameter Investigation
        |
        v
Independent Test Evaluation
        |
        v
Performance Comparison and Analysis
```

## Technologies and Tools

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Deep Learning | PyTorch |
| Audio Processing | Librosa |
| Numerical Computing | NumPy |
| Data Analysis | Pandas |
| Machine Learning | Scikit-learn |
| Visualization | Matplotlib, Seaborn |
| Progress Monitoring | tqdm |
| Development Environment | Kaggle Notebooks |
| GPU Acceleration | CUDA |


## Research Considerations

- Patient-independent evaluation to reduce data leakage.
- Consistent preprocessing across all experiments.
- Reproducibility through multiple random seeds.
- Investigation of class imbalance and minority-class performance.
- Appropriate reporting of mean and standard deviation.
- Statistical comparison where sufficient experimental evidence is available.
- Careful interpretation of results for underrepresented disease categories.

## Future Research Directions

- Investigate additional CNN and hybrid deep learning architectures.
- Explore transfer learning for respiratory sound classification.
- Investigate data augmentation and class imbalance mitigation.
- Explore attention-based feature extraction.
- Evaluate model robustness and generalization.
- Investigate explainable AI techniques for model interpretation.
- Conduct statistical comparisons across architectures and optimizers.
- Explore the potential for practical computer-assisted respiratory assessment.



---

**Disclaimer:** This project is intended for academic research and experimental evaluation. It is not a clinically validated diagnostic system and should not replace professional medical assessment.
