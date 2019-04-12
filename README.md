# <center> Environmental Sound Classification(ESC) </center>
![spectrogram and wave](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/download.png)
The ESC-50 dataset is a labeled collection of 2000 environmental audio recordings of environmental sound.

The dataset consists of 5-second-long recordings organized into 50 semantical classes (with 40 examples per class) loosely arranged into 5 major categories:
<table>
  <tr><h3>
    <th align = 'left' >Animals</th>
    <th align = 'left' >Natural soundscapes & water sounds</th>
    <th align = 'left' >Human, non-speech sounds</th>	
    <th align = 'left' >Interior/domestic sounds</th>
    <th align = 'left' >Exterior/urban noises</th>
  </tr>
  <tr>
    <td>Dog</td>
    <td>Rain</td>	
    <td>Crying baby</td>
    <td>Door knock</td>
    <td>Helicopter</td>
  </tr>
  <tr>
    <td>Roosters</td>
    <td>Sea waves</td>
    <td>Sneezing</td>	
    <td>Mouse click</td>
    <td>Chainsaw</td>
  </tr>
  <tr>
    <td>Pig</td>
    <td>Crackling fire</td>
    <td>Clapping</td>	
    <td>Keyboard typing</td>
    <td>Siren</td>
  </tr>
  <tr>
    <td>Cow</td>
    <td>Crickets</td>
    <td>Breathing</td>	
    <td>Door, wood creaks</td>
    <td>Car horn</td>
  </tr>
  <tr>
    <td>Frog</td>
    <td>Chirping birds</td>
    <td>Coughing</td>	
    <td>Can opening</td>
    <td>Engine</td>
  </tr>
  <tr>
    <td>Cat</td>
    <td>Water drops	</td>
    <td>Footsteps</td>	
    <td>Washing machine	</td>
    <td>Train</td>
  </tr>
  <tr>
    <td>Hen</td>
    <td>Wind	</td>
    <td>Laughing</td>	
    <td>Vacuum cleaner</td>
    <td>Church bells</td>
  </tr>
  <tr>
    <td>Insects (flying)</td>
    <td>Pouring water</td>
    <td>Brushing teeth</td>	
    <td>Clock alarm</td>
    <td>Airplane</td>
  </tr>
  <tr>
    <td>Sheep</td>
    <td>Toilet flush</td>
    <td>Snoring</td>	
    <td>Clock tick</td>
    <td>Fireworks</td>
  </tr>
  <tr>
    <td>Crow</td>
    <td>Thunderstorm</td>
    <td>Drinking, sipping</td>	
    <td>Glass breaking	</td>
    <td>Hand saw
</td>
  </table>

Clips in this dataset have been manually extracted from public field recordings gathered by the <a href = http://freesound.org> Freesound.org</a> project. The dataset has been prearranged into 5 folds for comparable cross-validation, making sure that fragments from the same original source file are contained in a single fold.

A more thorough description of the dataset is available in the original <a href = http://karol.piczak.com/papers/Piczak2015-ESC-Dataset.pdf> paper </a> with some supplementary materials on GitHub: <a href =https://github.com/karoldvl/paper-2015-esc-dataset>ESC: Dataset for Environmental Sound Classification - paper replication data.</a>

## Download
The dataset can be downloaded as a single .zip file (~600 MB):

<a href = https://github.com/karoldvl/ESC-50/archive/master.zip> Download ESC-50 dataset</a>
<a href ='https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/classes.csv'>superviser(y/targets)</a>

## Project Overview
The proposal evaluates the potential of convolutional neural networks in classifying short audio clips of environmental sounds. We trained the model and observed that existing dataset is insufficient to get the good accuracy, So we did <b>Data Augmentation</b> We added white noise to copy of existing dataset, so now we have 4000 training example. The 10% data is used to test the model and 10% of remaining data to evaluate the model.

## Setup
The neccessary libraries to run the code.
## re
## cv2
## os
## numpy as np
## pandas as pd
## librosa
## librosa
## matplotlib
## tqdm
## scipy
## IPython
## sklearn
## keras

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
