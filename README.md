# MultiFeature Beat Tracking (Information Gain and Regularity)
- [How to use](#how-to-use)
- [MultiFeature Beat tracker -> Python jupyter notebook example](http://nbviewer.jupyter.org/github/JoseRZapata/MultiFeatureBeatTracking/blob/master/MultiFeatureBeattracking.ipynb)
- [Essentia Implementation](#essentia-implementation-fast)
- [Application](#application)

Submission of the Multi Feature Beat tracker to the MIREX 2013 Audio Beat Tracking task,
Using the Beat tracking estimation results from 6 different onset detection functions:

- Complex Spectral Difference
- Energy Flux
- Harmonic Function
- Sub Bands weight
- Phase Slope Function
- Spectral Flux Log Filtered

This beat tracker uses a commitee strategy to obtain the most agreement estimation using the information Gain Measure over six beat estimations.
The output of the algorithm is the beat estimation times with a confidence value and the Tempo estimation.
MMA confidence value was only validated for the MultiBtInf algorithm.


This configuration (Multi InfG) with six onset detection funtions and the comparison results with other Beat trackers were presented in:
J.R. Zapata, M. Davies and E. Gómez, "Multi-feature beat tracker," IEEE/ACM Transactions on Audio, Speech and Language Processing. 22(4), pp. 816-825, 2014. http://dx.doi.org/10.1109/TASLP.2014.2305252

The beat tracker uses a commitee strategy to obtain the most agreement estimation using the information Gain Measure (MultiBtIfn) or Regularity (MultiBtReg).

## How to use
### Python
In Python can be use using Essentia, there is an [example in a jupyter notebook](http://nbviewer.jupyter.org/github/JoseRZapata/MultiFeatureBeatTracking/blob/master/MultiFeatureBeattracking.ipynb)
### Matlab
In MATLAB 2013a or Higher The algorithm is called as follows: (Only .Wav audio files)

<code>$ MultiBtInf('InputAudioFile.wav','OutputTextFile.txt'); </code>

<code>$ MultiBtReg('InputAudioFile.wav','OutputTextFile.txt'); </code>

Output:
- OutputTextFile.txt       -> text file with the estimation of Beat positions in seconds of the audio file
- Tempo-OutputTextFile.txt -> text file with the Tempo estimation in bpm 
- MMA-OutputTextFile.txt   -> text file with the confidence value of the estimation (MMA). (Only for MultiBtInf)


The quality of beats estimation based on the computed confidence value:

- [0, 1)      -> very low confidence, the input signal is hard for the employed candidate beat trackers
- [1, 1.5]    -> low confidence
- (1.5, 3.5]  -> good confidence, accuracy around 80% in AMLt measure
- (3.5, 5.32] -> excellent confidence

## Essentia Implementation (Fast)

The Multi Feature Beat Tracker is Implemented in ESSENTIA (http://essentia.upf.edu), there is an example in a jupyter notebook [http://nbviewer.jupyter.org/github/JoseRZapata/MultiFeatureBeatTracking/blob/master/MultiFeatureBeattracking.ipynb](http://nbviewer.jupyter.org/github/JoseRZapata/MultiFeatureBeatTracking/blob/master/MultiFeatureBeattracking.ipynb)

This configuration only uses 5 onset detection functions due to the disproportionately high computational cost of including the Phase Slope Function

Essentia is a C++ library of algorithms to extract features from audio files, including Python bindings.

Multifeature Beat tracker essentia documentation:
http://essentia.upf.edu/documentation/reference/std_BeatTrackerMultiFeature.html

Essentia Official releases:

- https://github.com/MTG/essentia/

D. Bogdanov, N. Wack, E. Gomez, S. Gulati, P. Herrera, O. Mayor, G. Roma, J. Salamon, J.R. Zapata, and X. Serra. 
Essentia: An audio analysis library for music information retrieval. International Society for Music Information Retrieval Conference (ISMIR'13),  493-498, 2013.

## Application

[Crypt of the NecroDancer](http://necrodancer.com/) is an award winning independent game. Players move on the beat of the music to navigate a dungeon and fight enemies. The game uses the Multi Feature Beat Tracker (implemented in Essentia) beat detection capabilities to allow users to play the game with songs from their own music library.




