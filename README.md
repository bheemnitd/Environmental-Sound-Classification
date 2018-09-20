# <center> Environmental Sound classification</center>
### Overview
The proposal evaluates the potential of convolutional neural networks in classifying short audio clips of environmental sounds. The model consisting one Relu activation and softmax activation with zero dropout. The audio set is converted into spectrogram and then model is trained. The classification is classified in 5 classes. The keras library is used over tensorflow.

### Data Preprocessing

### Variables Discription
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

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. First of all the  dataset is cloned from the github repository into google colab environment. After cloning, i fetched every audio clips name into variable audio_files and then i explored some dataset’s example in form of spectrogram, waveform and  audible form. After that i loaded the audio clips into the variable temporary_audio_files. Keep in mind audio_files contain files name whereas temporary_audio_files keeps the audio clips data, after that i replicated all audio into itself and placed into replicated_audio_files, and then all audio converted into spectrogram and stored into replicated_spectrogram_files. For replicating i used numpy.

replicated_audio_files = np.c_[ temporary_audio_files, temporary_audio_files ]
