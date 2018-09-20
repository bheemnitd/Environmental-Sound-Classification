# <center> Environmental Sound classification</center>
### Overview
The proposal evaluates the potential of convolutional neural networks in classifying short audio clips of environmental sounds. The model consisting one Relu activation and softmax activation with zero dropout. The audio set is converted into spectrogram and then model is trained. The classification is classified in 5 classes. The keras library is used over tensorflow.

Data Preprocessing
 Variables under Common Section

data - store one audio file.
sampling_rate - keep sampling rate of audio file.
spectrogram - keep one spectrogram data to plot.
audio_files - store all audio files name.
number_of_audio_files - total number(counting) of original audio files.
temporary_audio_file  -  one one original audio file.
temporary_audio_files -  store all original audio files.
II.     Variables under Replicated data(10 seconds audio files(2000) ).

replicated_audio_files - store all audio files after replication.
replicated_spectrogram_files - keep spectrogram of all replicated files.
supervisor - store supervisor(target, y) which is extracted from audio_files.
train_x - prepared training(feature) data to train the model after splitting from replicated_spectrogram_files.
test_x - prepared testing(feature) data to train the model after splitting from replicated_spectrogram_files.
train_y -  prepared testing(target/supervisor/ y) data to train the model after splitting from replicated_spectrogram_files.
test_y -  prepared testing(target/supervisor/ y) data to train the model after splitting from replicated_spectrogram_files.
t0 - store the model training time.
subclasses - store all subclasses sounds name. 
classes - store all subclasses sounds categories name.
Prediction - keep the prediction of testing sound.


III.     Variables under Augmentation (5 seconds audio files(6000) ).

size_of_audio_files - size of one audio files.
augmented_audio_files1 - store audio with white noise of original files..
augmented_audio_files2 - store shifted audio of original files.
augmented_audio_files3 - store original(temporary_audio_files) + augmented_audio_files1 + augmented_audio_files2, so the number of files in augmented_audio_files3 variable becomes 6000.
number_of_audio_files - store total number(counting) of original audio files.
augmented_spectrogram_files - store keep spectrogram of all replicated files.
number_of_training_example - store number of training example after augmentation.
y - store supervisor/target after augmentation.
Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. First of all the  dataset is cloned from the github repository into google colab environment. After cloning, i fetched every audio clips name into variable audio_files and then i explored some dataset’s example in form of spectrogram, waveform and  audible form. After that i loaded the audio clips into the variable temporary_audio_files. Keep in mind audio_files contain files name whereas temporary_audio_files keeps the audio clips data, after that i replicated all audio into itself and placed into replicated_audio_files, and then all audio converted into spectrogram and stored into replicated_spectrogram_files. For replicating i used numpy.

replicated_audio_files = np.c_[ temporary_audio_files, temporary_audio_files ]
