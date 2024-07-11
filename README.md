# Application of Convolutional Neural Network Methods in Muscle Fatigue Classification Based on Handgrip Strength Estimation Using Surface Electromyography (sEMG)
This study classifies muscle fatigue using custom CNN and ResNet50 models, based on handgrip strength estimations from Surface Electromyography (sEMG) signals. The Short-Time Fourier Transform (STFT) converts sEMG signals into time-frequency representations for CNN input. 

# Abstract
Muscle fatigue is characterized by a decline in maximal muscle strength during contraction, often caused by prolonged, intense contractions. This study classifies normal (non-fatigued) muscles versus fatigued muscles through measurements during Maximal Voluntary Contractions (MVCs). Using the Flexor Digitorum Superficialis (FDS) muscle as the basis for Surface Electromyography (sEMG), handgrip strength serves as a key indicator of neuromuscular function, commonly used to assess health and performance. The study involves male and female students aged 20-22 as subjects. EMG signals are collected using Bitalino sensors while subjects grip a handgrip with their non-dominant hand and follow contraction instructions. MVC tests are conducted to record maximal force output before, after, and/or during continuous instructions to measure fatigue patterns. The decline in force output measured in these tests indicates muscle fatigue patterns. The Bitalino sensors connect to a computer with OpenSignals to monitor the EMG signals, with electrodes placed on the FDS muscle. Convolutional Neural Network (CNN) deep learning models are used for data processing and analysis, enabling high-accuracy identification of muscle activity patterns and changes.

# Problem Statement 
This study aims to develop a classification method for Electromyography (EMG) signals using Convolutional Neural Networks (CNN) to distinguish between handgrip signals from normal patients and those experiencing muscle fatigue. EMG is commonly used in healthcare to record electrical activity from muscles during contraction. Here, the focus is on analyzing handgrip muscle signals, representing the muscle activity involved in gripping.

Muscle fatigue during exercise is a common physiological occurrence that can reduce energy capacity and performance, increasing the risk of sports injuries. Thus, recognizing fatigue based on surface EMG signals plays a crucial role in sports training, rehabilitation, and movement identification. Early detection of muscle fatigue through EMG signal analysis has significant potential for monitoring patient health, especially in physical rehabilitation and sports. Accurate classification methods can help identify changes in muscle activity patterns related to fatigue, providing valuable insights for patient care and management.

# Data Acquisition Method
## Preparation
1.	Conduct data collection in a room with a temperature between 25-28°C. Adjust the air conditioning as needed to maintain this range, as the equipment is temperature-sensitive.
2.	Ensure all equipment is prepared and thoroughly checked, including BiTalino, electrodes, and the laptop running OpenSignal software.
3.	The subject should sit comfortably and relaxed. If tense, guide them to take deep breaths.
4.	Data is collected from the non-dominant hand (left hand). Ensure the subject's hand does not touch clothing, especially cotton.
5.	The subject must remain focused, maintain a neutral facial expression, and avoid speaking, smiling, looking around, or moving their mouth.
6.	The laptop should not be charged during data collection to avoid electrical noise.
## Data Collection:
<p align="center">
<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/Data%20Acquisition%20Method.png"  width="40%" height="35%"/>

### 1.	Fatigue Measurement:
- Conduct Maximal Voluntary Contractions (MVCs) tests to measure force output during maximal voluntary effort.
- Record maximal force output before, during, and after continuous instruction to identify muscle fatigue patterns.
- Subjects grip a handgrip with maximum strength for 5 seconds (data not recorded), rest for 5 minutes, and then grip at 70% of the maximal force for subsequent tests.
### 2.	Fatigue and Non-Fatigue Data:
- Use OpenSignals software connected to BiTalino sensors to record EMG signals from the FDS muscle of the non-dominant hand.
- Follow the time sequence: stabilize (no movement), grip handgrip for 10 seconds at stable strength (threshold MVC), relax for 5 seconds, and grip again for 5 seconds at full strength to measure fatigue (MVCt). This sequence records non-fatigue data.
- To obtain fatigue data, the subject repeats the handgrip movement until MVCt > MVCref, noting the repetitions. If this condition is met, record the final data following the same procedure as for non-fatigue data.

# Pre-Processing
### Signal Preprocessing
<p align="center">
<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/STFT_Signal.png"  width="40%" height="35%"/>

- Zero Baseline Correction
- Absolute Signal
- Data Normalization
- Data Filtering
- Convert Spectrogram Data to Short-Time Fourier Transform (STFT)
  
### Image Preprocessing
- Data Augmentation
<p align="center">
<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/Image_Preprop.png"  width="40%" height="35%"/>


# Model

| Model          | Number of Parameters | Model Structure |
|----------------|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Custom CNN** | 25.710.657           |<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/CNN_model.png"  width="40%" height="35%"/>            |
| **ResNet50**   | 23.850.113           | <img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/ResNet50_model.png"  width="50%" height="50%"/>      |

# Result

|                       | Custom CNN           | ResNet50 |
|-----------------------|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Accuracy**          |<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/CNN_Acc.png"  width="80%" height="80%"/>| <img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/ResNet50_Acc.png"  width="80%" height="80%"/>|
| **Model Loss**        |<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/CNN_Loss.png"  width="80%" height="80%"/>|<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/ResNet50_Loss.png" width="80%" height="80%"/>|
| **Confussion Matrix** |<img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/CNN_CF.png"  width="80%" height="80%"/>| <img src="https://github.com/kusumowidi/sEMG-Muscle-Fatigue-Clasification/blob/main/result/ResNet50_CF.png"  width="80%" height="80%"/>|

