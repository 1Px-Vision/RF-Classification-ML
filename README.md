# RF-Classification-ML
![C_RF](https://github.com/1Px-Vision/RF-Classification-ML/blob/main/Dashboard_RF.jpg)
## Overview
This dashboard provides real-time RF signal analysis using an RTL-SDR device. It continuously acquires and processes radio signals, displaying the Power Spectrum, Spectrogram (Waterfall), and Modulation Classification Results.
The system uses a deep learning-based classification model (ONNX format) to identify different modulation types such as BPSK, QPSK, GMSK, FM, OOK, OQPSK, 8PSK, 16QAM, AM-DSB-WC, AM-DSB-SC.

![S_RF](https://github.com/1Px-Vision/RF-Classification-ML/blob/main/Classification_RF.jpg)

### **1. Getting Started**

- Connect the RTL-SDR to your computer.
- Launch the Dashboard by running the Python script.
- Click Start/Stop to begin or halt real-time signal acquisition.

### **2. User Interface Explanation**
- Top Control Bar
- **Center Frequency (Hz):** Displays the current center frequency set for the SDR.
- **LED Indicator (Red/Green):** Shows whether the system is running or stopped.
- **Start/Stop Button:** Toggles real-time signal processing.
- **Quit Button:**  Exits the application.

### Main Analysis Panel

#### Power Spectrum (FFT Display)
- Shows the frequency spectrum of the received signal.
- **X-axis:** Frequency in MHz.
- **Y-axis:** Power Density in dB.
- **Blue Line:** Represents the signal's power spectrum.
  
#### Classification Modulation (Bar Chart)
- Displays real-time classification of modulation schemes.
- **X-axis:** Accuracy (%) of classification.
- **Y-axis:** Different modulation types detected.

#### Spectrogram (Waterfall Display)
- Shows the time-frequency representation of the signal.
- **X-axis:** Frequency in MHz.
- **Y-axis:** Time evolution of frequency components.
- **Color Scale:** Represents signal power (yellow = strong, blue = weak).

### Right Panel – Configuration Settings

#### Control Tab
- Selects device type (RTL-SDR, HackRF, Airspy).
- Adjusts **LNA Gain** manually or enables Auto Gain.
- Chooses a **Neural Network** (CNN, ResNet, VGG10, etc.) for classification.
- Selects **Quantization Mode** (e.g., 32-bit, 8-bit, 4-bit) for optimized performance.

#### Configure Tab

- **Corr. PPM:** Frequency correction in parts per million.
- **Center Frequency (MHz):** Adjust the tuning frequency.
- **Start/End Frequency (MHz):** Defines the scan range when in Scan Mode.
- **Channels:** Number of frequency bands to process.
- **Mode:** Choose between Multichannel or Scan Mode.
- **Sample Rate:** Selects SDR sampling rate (e.g., 2.048 MSPS).
- **Read Sample:** Defines the number of IQ samples acquired per read.
  
### Help Tab
Contains usage instructions, troubleshooting steps, and contact details.

## 3. How to Use
### 1- Start Real-Time Processing
- Click Start/Stop to begin RF signal acquisition.
- The LED indicator will turn Green.
- The Power Spectrum, Spectrogram, and Classification Chart will update in real-time.
  
### 2- Modify Settings
- Adjust the Center Frequency, Gain, or Neural Network Model.
- Switch between Multichannel Mode and Scan Mode.

### 3- Stop Processing
- Click Start/Stop again to stop data acquisition.
- The LED indicator will turn Red.

### 4- Exit the Application
- Click the Quit button to close the dashboard.

