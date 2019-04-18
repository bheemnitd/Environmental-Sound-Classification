# <center> Environmental Sound Classification(ESC) </center>
![spectrogram and wave](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/download.png)
## Project Overview
The proposal evaluates the potential of convolutional neural networks in classifying short audio clips of environmental sounds. We trained the model and observed that existing dataset is insufficient to get the good accuracy, So we did <b>Data Augmentation</b> We added white noise to copy of existing dataset, so now we have 4000 training example. The 10% data is used to test the model and 10% of remaining data to evaluate the model. After augmentation we trained the model with 4 Conv2D, 4 relu activaion, 1 softmax activation, 4 MaxPooling2D, 1 Dropout and 1 Desnse layer. We used 30 epochs and achived % of training accuracy and % of Validation accuracy.

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

<a href = https://github.com/karoldvl/ESC-50/archive/master.zip> Download ESC-50 dataset</a><br>
<a href='https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/classes.csv'>Classes</a>


## Setup
Install these libraries to run the code.
<li> re
<li> cv2
<li> os
<li> numpy
<li> pandas
<li> librosa
<li> librosa
<li> matplotlib
<li> tqdm
<li> scipy
<li> IPython
<li> sklearn
<li> tensorflow/tensorflow-gpu
<li> keras

## Variables Discription<br>
**audio_files** - store all audio file and corresponding class.<br>
**sampling_rate** - which keep the flow of number of element per second of audio files.<br>
**spectrogram** - keep spectrogram of audio file.<br>
**augmented_audio_files** - store audio with white noise of original files and then combined with **audio_files**<br>
**SPEC_H** - spectrogram height.<br>
**SPEC_W** - spectrogram width.<br>
**audio** - one audio file.<br>
**x** - x is just a temporary variable for get audio file **x_train** after coverting into spectrogram assigned to the same **x_train** variable.<br>

## Testing on Unseen data.
![spectrogram](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/Selection_004.png)
![Waveform](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/Selection_005.png)
![Audible](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/Selection_006.png)
![Audible](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/Selection_007.png)
## Summary of model.
![Audible](https://github.com/bheemnitd/EnvironmentalSoundClassificationFromKeras/blob/master/Selection_008.png)

