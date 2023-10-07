# Signal Onset Detection and Audio Manipulation
## Overview
This repository presents an end-to-end system for signal onset detection and audio manipulation. The project is structured around detecting onsets in an audio signal and then utilizing those onset points to manipulate the original audio. The main focus is on:High-pass filtering the audio.
Detecting onsets in the high-pass filtered signal.
Manipulating the audio based on detected onsets (like reversing sections).
## Key Features
### High-pass Filter: 
Filters out low-frequency components of the audio.
### Onset Detection:
Detects points (in samples) in the audio signal where there's a significant change, often indicating the start of a sound event.
### Reverse Chop: 
Reverses the audio signal in sections that are bookended by onset points, provided the sections are shorter than a given threshold.
### Random Permutation:
Randomly reorders the chopped audio sections to create a new audio sequence.
## Instructions
###  Prerequisites:
### Required Libraries:
numpy, scipy, librosa, and matplotlib.
### Audio Data:
Place your audio .wav files inside the uploaded_audio directory.
### Running the Code:
Load your desired .wav file.
Apply the high-pass filter to the audio signal.
Detect the onsets in the high-pass filtered signal.
Use the detected onsets to reverse chop or permute the original audio.
Listen to the manipulated audio using Audio().
## Technical Details
### highpass_filter(): 
Applies a high-pass Butterworth filter to an audio signal.
### onSetDetect():
Detects onset points in the high-pass filtered audio signal.
### betarevchop():
Uses detected onsets to reverse sections of the original audio signal that are smaller than a given threshold.
### NewOG and HelpMe: 
Store manipulated audio arrays. NewOG retains the original order, while HelpMe contains randomly permuted sections.
Results
The manipulated audio can be significantly different from the original, depending on the detected onsets and the subsequent operations performed. The visualizations (using plt.plot()) can help observe the alterations made to the waveform.

## Authors and Contributions
Quincy: Loaded and displayed the original audio.
Michael: Implemented the betarevchop() function.
Isaac: Developed the onset detection mechanism.
J@h: Manipulated the audio based on detected onsets and visualized the results.
Notes
The onset detection is sensitive to the parameters and threshold used. Adjustments might be needed based on the specific characteristics of the audio signal.
Audio manipulations, especially random permutations, can result in abrupt and unpredictable sound variations.
