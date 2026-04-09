# heartbeat-arrhythmia-classification-using-deep-learning

## Overview
This repository contains the code for a deep learning project aimed at predicting heartbeat arrhythmia classes using a custom model built with a combination of 1D Convolutional Neural Network (CNN), Bidirectional Gated Recurrent Unit (GRU), and Fully Connected layers. The model is trained and evaluated on six classes from the MIT-BIH Arrhythmia Database.


## Data Preprocessing
1. **Signal Filtering**:
   - **Moving Average Filter**: Used to smooth the ECG signals by averaging the signal values within a specific window.
   - **Butterworth Lowpass Filter**: Applied to remove high-frequency noise from the ECG signals while preserving the useful frequency components.
   - **Median Filter**: Utilized to remove artifacts and noise by replacing each data point with the median of the neighboring data points.

2. **Signal Segmentation**:
   - Custom segmentation approach developed to divide the ECG signals into meaningful segments for further analysis and model training.

3. **Data Augmentation**:
   - Techniques such as adding noise, scaling, and shifting were applied to augment the data, enhancing the model's robustness and generalization capabilities.

4. **Data Preparation**:
   - ECG signals were converted to 3D numpy arrays.
   - Labels were encoded into categorical format suitable for model training.

## Model Architecture
- **1D Convolutional Neural Network (1D CNN)**:
  - Used for feature extraction from the ECG signal segments.
  - Several convolutional layers followed by max-pooling layers to capture spatial hierarchies.
  
- **Bidirectional Gated Recurrent Unit (Bi-GRU)**:
  - Implemented to capture temporal dependencies and sequence information in the ECG data.
  - Bi-directional processing allows the model to have context from both past and future time steps.
  
- **Fully Connected Layers**:
  - Dense layers that take the extracted features and classify them into one of the six arrhythmia classes.

## Training and Evaluation
- The model was trained on preprocessed and segmented ECG signals using the following setup:
  - **Optimizer**: Adam
  - **Loss Function**: Categorical Crossentropy
  - **Batch Size**: 1000
  - **Epochs**: 20

- Various evaluation metrics were used to assess the model's performance:
  - **Accuracy**: Overall correctness of the model's predictions.
  - **F1 Score**: Harmonic mean of precision and recall.
  - **ROC Curve**: Receiver Operating Characteristic curve to visualize the trade-off between sensitivity and specificity.
  - **Confusion Matrix**: To show the detailed performance of the classifier.
  - **Classification Report**: Provides precision, recall, and F1 score for each class.

## Results
- **Training Accuracy**: 99.44%
- **Testing Accuracy**: 99.24%

The model demonstrated high accuracy and robustness in predicting arrhythmia classes, indicating its potential for real-world applications in medical diagnostics.

## Dependencies
- Python 3.7+
- NumPy
- Pandas
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- SciPy

## Acknowledgments
- The MIT-BIH Arrhythmia Database was used for this project.
- Inspiration and guidance were drawn from various research papers and online resources on deep learning and ECG signal processing.
