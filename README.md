# PredItSpeechInt

The PredItSpeechInt (Predicting Italian Speech Intelligibility) project aims at developing an Automatic Speech Recognition (ASR) system designed to work as a predictor of speech intelligibility in the presence of noise in the context of Matrix Sentence Tests With Closed Speech Corpora [1]. The project is focused on the Italian language and its predicting capabilities are tested with previously performed Italian matrix sentence human-listening tests [2], but the PredItSpeakInt code infrastructure should work for any language with minor modifications.

The ASR is based on the [Kaldi Speech Recognition Toolkit](http://kaldi-asr.org/) and it is trained by audio data obtained by mixing a clean speech corpus collected for the purpose with noise maskers with different types of spectro-temporal characteristics, employed to account for different aspects of masking such as energetic masking, amplitude modulation masking and informational masking.

1. ***HabeasCorpus***

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Contains anything involved in 1) the design and collection of the clean speech corpus; 2) audio manipulation; 3) mixing with established noise maskers; 4) data preparation as input training material for Kaldi.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In particular, the design and collection of the speech corpus are performed by two standalone python gui applications, while 2)-4) are based on various python scripts. The actual recording is performed by the external command line application [SoX](http://sox.sourceforge.net/) and it will work with any sound interface or microphone recognized by SoX. The training data used in the experiments has the same structure and vocabulary as the matrix sentences used for testing.

2. ***kaldi-fork***

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Fork of the Kaldi toolkit with custom designed feature extractors, such as the AMFB filterbanks [1]. 

3. ***kaldi-gpu-docker***

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Build kaldi inside docker containers with option for CUDA support

This project is part of an ongoing collaboration between the ISOF-CNR Institute (I), the University of Ferrara (I) and the University of Bologna (I).

**References:**

[1] C. Spille et al., "Predicting speech intelligibility with deep neural networks", Computer Speech & Language 48 (2018) 51-66

[2] G. Puglisi et al., "An Italian matrix sentence test for the evaluation of speech intelligibility in noise", International Journal of Audiology 54 (2015) - (Issue 2: Overcoming Language Barriers: Matrix Sentence Tests With Closed Speech Corpora)
