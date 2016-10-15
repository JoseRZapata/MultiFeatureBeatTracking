MultiFeature Beatracking (Regularity)
=========================================== 

Submission of the Multi Feature Beat tracker to the MIREX 2013 Audio Beat Tracking task,
Using the Beat tracking estimation results from 6 different onset detection functions:

• Complex Spectral Difference
• Energy Flux
• Harmonic Function
• Sub Bands weight
• Phase Slope Function
• Spectral Flux Log Filtered

This configuration (Multi InfG) of onset detection funtions and the comparing results with other Beat trackers were presented in J.R. Zapata, M. Davies and E. Gómez, "Multi-feature beat tracker," IEEE/ACM Transactions on Audio, Speech and Language Processing. 22(4), pp. 816-825, 2014. http://dx.doi.org/10.1109/TASLP.2014.2305252.

The beat tracker uses a commitee strategy to obtain the most agreement estimation using the Regularity Measure.

For more information:

J.R. Zapata, M. Davies and E. Gómez, "Multi-feature beat tracker," IEEE/ACM Transactions on Audio, Speech and Language Processing. 22(4), pp. 816-825, 2014. http://dx.doi.org/10.1109/TASLP.2014.2305252

J.R. Zapata, A. Holzapfel, M.E.P. Davies, J.L. Oliveira, F. Gouyon, "Assigning a confidence threshold on automatic beat annotation in large datasets", International Society for Music Information Retrieval Conference (ISMIR'12), pp. 157-162, 2012. 
http://ismir2012.ismir.net/event/papers/157_ISMIR_2012.pdf

Platform 
----------
MATLAB 2013a or Higher

How to use
----------

In MATLAB The algorithm is called as follows: (Only .Wav audio files)

<code>$ MultiBtReg('InputAudioFile.wav','OutputTextFile.txt'); </code>

Ex:
<code>$ MultiBtReg('train9.wav','output.txt'); </code>

The output is a Text file with the Beat positions in seconds of the audio file

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




