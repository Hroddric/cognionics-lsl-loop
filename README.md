# EEG experiment set up with Cognionics data capture using Lab Streaming Layer and stimuli presentation with PsychoPy
These files contain different functions and classes that help setup experiments with the EEG headsets from Cognionics, Inc. (but can easily be modified to fit other EEG systems that use Lab Streaming Layer). The experiment all these scripts were made for consists of a BCI Speller using emojis instead of letters.

### Introduction to usage (not intended for general public)
The Cognionics, Inc. EEG headset connects to a computer via Bluetooth using the USB Stick provided with the headset and the Cognionics Data Acquistion Software (DAQ) as software that reads the bluetooth signal. This software can export the data to the laboratory network using Lab Streaming Layer (LSL). These data streams on the network can be found with the different Lab Streaming Layer interfaces. In this case, we use the Python interface. With it we get the data from the stream and process it, both in real time and saving in files (.npz).

While the acquisition of data happens, the stimuli are shown on the screen: images that are augmented at different times. These stimuli provoke the appearance of event related potentials (ERP), which when read with the EEG are shown as P300 waves. Using different techniques (like Linear Discrimination Analysis (LDA) or Neural Networks (NNs)) one can process these signals and detect when the P300 happened and relate that to one of the augmentations of the images. All this can be done in real time, as mentioned before, thanks to the "real time" streaming of the data obtained by the headset throught LSL. After processing the signals and finding which image was the user looking at, the result is displayed and a choice can be made by the user, showing if that result coincides with the actual Ground Truth.

At this point in time (2nd of July 2018) the whole data acquisition and stimuli presentation is set up. Only the processing part (LDA or NNs) is needed to be able to test the whole system.
