MultiFeature Beat tracking (Information Gain)
=============================================

Submission of the Multi Feature Beat tracker to the MIREX 2013 Audio Beat Tracking task,
Using the Beat tracking estimation results from 6 different onset detection functions:

- Complex Spectral Difference
- Energy Flux
- Harmonic Function
- Sub Bands weight
- Phase Slope Function
- Spectral Flux Log Filtered

This beat tracker uses a commitee strategy to obtain the most agreement estimation using the information Gain Measure over six beat estimations.
The output of the algorithm is the beat estimation times with a confidence value. 

This configuration (Multi InfG) with six onset detection funtions and the comparison results with other Beat trackers were presented in:
J.R. Zapata, M. Davies and E. Gómez, "Multi-feature beat tracker," IEEE/ACM Transactions on Audio, Speech and Language Processing. 22(4), pp. 816-825, 2014. http://dx.doi.org/10.1109/TASLP.2014.2305252

The beat tracker uses a commitee strategy to obtain the most agreement estimation using the information Gain Measure.

Platform 
----------
MATLAB 2013a or Higher

How to use
----------

In MATLAB The algorithm is called as follows: (Only .Wav audio files)

<code>$ MultiBtInf('InputAudioFile.wav','OutputTextFile.txt'); </code>

Ex:
<code>$ MultiBtInf('train9.wav','output.txt'); </code>

The output is a text file with the Beat positions in seconds of the audio file and
a text file with the confidence value of the estimation (MMA).
MMA confidence value was only validated with the MultiBtInf approach
The quality of beats estimation based on the computed confidence value:

- [0, 1) very low confidence, the input signal is hard for the employed candidate beat trackers
- [1, 1.5] low confidence
- (1.5, 3.5] good confidence, accuracy around 80% in AMLt measure
- (3.5, 5.32] excellent confidence

Essentia Implementation
-----------------------

The Multi Feature Beat Tracker is Implemented in ESSENTIA (http://essentia.upf.edu)

This configuration only uses 5 onset detection functions due to the disproportionately high computational cost of including the Phase Slope Function

Essentia is a C++ library of algorithms to extract features from audio files, including Python bindings.

Multifeature Beat tracker essentia documentation:
http://essentia.upf.edu/documentation/reference/std_BeatTrackerMultiFeature.html

Essentia Official releases:

* https://github.com/MTG/essentia/

D. Bogdanov, N. Wack, E. Gomez, S. Gulati, P. Herrera, O. Mayor, G. Roma, J. Salamon, J.R. Zapata, and X. Serra. 
Essentia: An audio analysis library for music information retrieval. International Society for Music Information Retrieval Conference (ISMIR'13),  493-498, 2013.



