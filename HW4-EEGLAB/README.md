# Homework 4 - EEGLAB Toolbox  
**EEG Preprocessing and ERP Analysis**

## Overview

This homework explores the impact of EEG preprocessing steps on Independent Component Analysis (ICA) and Event-Related Potentials (ERP). By manipulating the order of preprocessing steps, we will observe the effects on ICA components, ERPs, and channel activity.

---

## Dataset Description

Participants performed three sessions of a 13-minute auditory search task. Each session included three types of stimuli:  
- **Standard (70%)**: 500 Hz pure tone lasting 60ms  
- **Deviant (15%)**: 1000 Hz pure tone lasting 60ms  
- **Distractors (15%)**: 1000 Hz white noise lasting 60ms  

All sounds ramped up and down over 5ms, with a presentation rate of 1 per second (random Gaussian jitter, SD = 25ms). Participants were instructed to respond to oddball stimuli by pressing a key.

### Experiment Details:
- **Channels**: 64 EEG channels
- **Sampling Frequency**: 256 Hz
- **Line Noise**: 50 Hz
- **Events**:
  - `response`: Response of the subject
  - `standard`: Standard tone (500 Hz, 60ms)
  - `oddball`: Oddball tone (1000 Hz, 60ms)
  - `noise`: White noise (1000 Hz, 60ms)
  - `standard_with_response`: Standard tone with an incorrect response
  - `oddball_with_response`: Oddball tone with a correct response
  - `noise_with_response`: White noise with an incorrect response

---

## Steps in Preprocessing

### **A. ICA Components: Cleaning the Signal**
The goal of this section is to understand how cleaning steps affect ICA components. The following steps are required before applying ICA:

1. **Remove extra channels**: Exclude GSR, Misc, Resp, and Temp channels.
2. **Remove signal bias**: Apply a FIR high-pass filter at 0.5 Hz.
3. **Plot Channels and Power Spectral Density (PSD)**:
   - Plot time-domain signals (channel data).
   - Plot PSD with the range 0-32 Hz, ensuring scalp maps are removed.

### **Methods for Signal Cleaning:**
We will plot ICA components before and after each of the following signal cleaning methods:

1. **Line Noise Cleaning** (50 Hz)
2. **Artifact Subspace Reconstruction (ASR)**
3. **Re-referencing the Data**: Apply average referencing or re-reference to channel "Cz."

Be sure to document the order of the processes used and plot the ICA components for each of the three methods as well as before any preprocessing.

---

### **B. ERP Analysis: Impact of Reference and ICA**

In this section, we will plot ERPs and assess the effects of reference and ICA on the ERP results.

1. **Extract Epochs**:
   - Extract epochs for `standard_with_response` and `oddball_with_response` events within a time window of -1s to 2s.
   - Remove baseline (-1s).

2. **ERP Plots**:
   - Plot ERPs with scalp maps.
   - Plot ERPs using a scalp/rectangular array.
   - Select the most prominent channel and:
     - Plot Channel ERP image.
     - Plot Channel time-frequency analysis for the selected channel.

### **Repetition of Part B**:
We will perform the ERP analysis twice:
1. **Before ICA**: Apply ICA and remove bad components before extracting epochs.
2. **After ICA**: Apply ICA and remove bad components after extracting epochs.

#### Preprocessing Steps:
- **Remove line noise** (50 Hz).
- **Use ASR** for artifact cleaning.
- **Reference**: Use either average reference, channel "Cz," or no reference.

---

## Output and Reporting

At each step of the analysis, the following plots and outputs are required:
- ICA component plots before and after each cleaning method.
- Channel data and PSD plots at various stages of preprocessing.
- ERP plots for both `standard_with_response` and `oddball_with_response` events.
- Channel ERP images and time-frequency analysis for the most prominent channel.
- Comparisons of ERP results before and after applying ICA.
