# <center> Environmental-Sound-Classification-ESC-using-neural-network</center>
<li>Audio feature extraction and classification with the ECS-50 data set audio dataset ECS-50 audio data is included. 
<li>It consists of 50 classes of different environmental sounds (sea waves, bay crying, etc.)</li>
<li>The main goal is to compare classification accuracies for the 6 tested classifiers.</li>
## Overview
The proposal evaluates the potential of convolutional neural networks in classifying short audio clips of environmental sounds. The model consisting one Relu activation and softmax activation with zero dropout. The audio set is converted into spectrogram and then model is trained. The classification is classified in 5 classes. The keras library is used over tensorflow.

## Data Preprocessing
### Variables Discription<br>
**data** - store one audio file.<br>
**sampling_rate** - keep sampling rate of audio file.<br>
**spectrogram** - keep one spectrogram data to plot.<br>
**audio_files** - store all audio files name.<br>
**number_of_audio_files** - total number(counting) of original audio files.<br>
**temporary_audio_file**  -  one one original audio file.<br>
**temporary_audio_files** -  store all original audio files.<br>
**size_of_audio_files** - size of one audio files.<br>
**augmented_audio_files1** - store audio with white noise of original files..<br>
**augmented_audio_files2** - store shifted audio of original files.<br>
**augmented_audio_files3** - store original(temporary_audio_files) + augmented_audio_files1 + augmented_audio_files2, so the number of files in augmented_audio_files3 variable becomes 6000.<br>
**number_of_audio_files** - store total number(counting) of original audio files.<br>
**number_of_training_example** - store number of training example after augmentation.<br>
**y** - store supervisor/target after augmentation.<br>

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. First of all the  dataset is cloned from the github repository into google colab environment. After cloning, i fetched every audio clips name into variable **audio_files** and then i explored some dataset’s example in the form of spectrogram, waveform and audible form. After that i loaded the audio clips into the variable **temporary_audio_files**. Keep in mind **audio_files** contain files name whereas **temporary_audio_files** keeps the audio clips data, after that processed data augmentation and then number of audio files becomes 6000.the audio clips are coverted into spectrogram and then model is trainind and also calculated training time.
## Spectrogram generation

For generating spectrogram i used librosa python library, by using the function melspectrogram .

![spectrogram](https://github.com/bheemnitd/Environmental-Sound-Classification-Keras/blob/master/Selection_019.png)

**spectrogram = librosa.feature.melspectrogram( data, sampling_rate )**

## Waveform generation.

For generating waveform i used librosa python library, by using the function waveplot.

![Waveform](https://github.com/bheemnitd/Environmental-Sound-Classification-Keras/blob/master/Selection_020.png)

**WaveForm = librosa.display.waveplot( data, sr = sampling_rate )**

## Audible  sound generation.

For generating audible sound i used IPython library, by using the function Audio

![Audible](https://github.com/bheemnitd/Environmental-Sound-Classification-Keras/blob/master/Selection_021.png)

**Audible = Audio( data, rate = sampling_rate )**

Runn the prediction 5 to 10 times to check the prediction.





