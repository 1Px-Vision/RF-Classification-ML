# RF-Classification-ML
![C_RF](https://github.com/1Px-Vision/RF-Classification-ML/blob/main/Dashboard_RF.jpg)
## Overview
This dashboard provides real-time RF signal analysis using an RTL-SDR device. It continuously acquires and processes radio signals, displaying the Power Spectrum, Spectrogram (Waterfall), and Modulation Classification Results.
The system uses a deep learning-based classification model (ONNX format) to identify different modulation types such as BPSK, QPSK, GMSK, FM, OOK, OQPSK, 8PSK, 16QAM, AM-DSB-WC, AM-DSB-SC.

![S_RF](https://github.com/1Px-Vision/RF-Classification-ML/blob/main/Classification_RF.jpg)


| **Modulation Type** | **Technology and Application** |
|---------------------|--------------------------------|
| **AM-SSB**         | Ideal for maritime and aviation emergencies, AM-SSB ensures long-distance voice communication with high power efficiency, making it crucial for rescue coordination over vast areas. |
| **AM-DSB-SC**      | Transmits both sidebands without a carrier, enhancing power efficiency but requiring precise synchronization. Used in disaster relief for long-distance emergency signals in military and governmental networks. |
| **FM**             | Widely used in VHF/UHF public safety and commercial radio, providing clear, noise-resistant audio for emergency teams. It ensures reliable coverage in various areas but degrades quickly over long distances without repeaters. |
| **OOK**            | A simple amplitude shift keying method, historically tied to Morse code, used in emergency beacons, distress signals, and survival radios for low-power communication. |
| **BPSK**           | Robust digital modulation resistant to noise, widely used in satellite-based rescue communications (e.g., Iridium, Inmarsat) for voice and data transmission in remote areas. Satellite distress beacons (EPIRBs [1], PLBs [2], and COSPAS-SARSAT [3]) enable global emergency messaging under weak signal conditions. |
| **QPSK**           | Efficient for disaster scenarios, supporting emergency communication via deployable LTE, temporary towers, and UAV relays, ensuring reliable transmission for first responders. |
| **OQPSK**          | OQPSK minimizes phase transitions, improving resilience against signal degradation in emergency communications. It is widely used in satellite-based distress signaling, such as COSPAS-SARSAT beacons and emergency transponders, due to its stability in weak or noisy conditions. |
| **8PSK**           | Encodes three bits per symbol for high spectral efficiency, enabling fast emergency data transmission in satellite and broadband systems, but requires a high SNR for accurate detection. |
| **GMSK**           | Primary modulation for GSM networks, essential for emergency calls and disaster recovery. Its smooth frequency transitions minimize interference, ensuring efficient communication in high-traffic scenarios. It also supports portable cell towers and drones for restoring mobile services during emergencies. |
| **16QAM**          | High-order modulation enables high-speed emergency broadband communication but requires strong signals. It supports rapid transmission of images, videos, and medical telemetry in urban rescues and UA


## Models and Training
Confusion matrices for CNN, VGG10, and ResNet models trained on the RadioML2018.01A dataset, comparing 32-bit precision against 1.5-bit quantization. The upper row displays results under standard 32-bit precision, while the lower row illustrates how classification performance changes with 1.5-bit quantization. Each confusion matrix reflects the models’ abilities to distinguish among different modulation types, thereby highlighting the impact of quantization on recognition accuracy.

![Confusion_Matrix](https://github.com/1Px-Vision/RF-Classification-ML/blob/main/Matrix_SDR_RF.jpg)

## Hardware-Integrated system RTL-SDR

![RTL](https://github.com/1Px-Vision/RF-Classification-ML/blob/main/RTL_SDR.jpg)

## Interface for real‐time signal capture

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

## 4. Troubleshooting

| Issue                              | Solution |
|------------------------------------|----------|
| **No signal appears in Power Spectrum** | Ensure RTL-SDR is connected properly and selected as the device. Check frequency and gain settings. |
| **Waterfall display is empty**     | Try increasing the sample rate or adjusting gain. |
| **Classification results seem incorrect** | Ensure the correct Neural Network model and Quantization settings are selected. |
| **App freezes**                    | Stop the acquisition, wait a few seconds, then restart. If needed, restart the application. |

## 5. Additional Notes
- Ensure that the RTL-SDR driver is properly installed before running the dashboard.
- The system requires **Python 3.x**, **Dash**, **Plotly**, **NumPy**, **Scipy**, **ONNX Runtime**, and **RTL-SDR** Python libraries.
- For best performance, use a dedicated machine with sufficient processing power.
