# BNCI 2015-012 PASS2D P300 dataset

BNCI 2015-012 PASS2D P300 dataset.

## Dataset Overview

- **Code**: BNCI2015-012
- **Paradigm**: p300
- **DOI**: 10.3389/fnins.2011.00099
- **Subjects**: 10
- **Sessions per subject**: 1
- **Events**: Target=1, NonTarget=2
- **Trial interval**: [0, 0.8] s
- **Runs per session**: 2
- **Session IDs**: session_1
- **File format**: gdf
- **Data preprocessed**: True
- **Contributing labs**: Berlin Institute of Technology, Fraunhofer FIRST

## Acquisition

- **Sampling rate**: 250.0 Hz
- **Number of channels**: 63
- **Channel types**: eeg=63
- **Channel names**: AF3, AF4, AF7, AF8, C1, C2, C3, C4, C5, C6, CP1, CP2, CP3, CP4, CP5, CP6, CPz, Cz, F1, F10, F2, F3, F4, F5, F6, F7, F8, F9, FC1, FC2, FC3, FC4, FC5, FC6, FCz, FT7, FT8, Fp1, Fp2, Fz, O1, O2, Oz, P1, P10, P2, P3, P4, P5, P6, P7, P8, P9, PO3, PO4, PO7, PO8, POz, Pz, T7, T8, TP7, TP8
- **Montage**: 10-20
- **Hardware**: Brain Products
- **Software**: Matlab
- **Reference**: nose
- **Sensor type**: wet Ag/AgCl electrodes
- **Line frequency**: 50.0 Hz
- **Online filters**: 0.1-250 Hz analog bandpass, then 40 Hz lowpass
- **Cap manufacturer**: EasyCap GmbH
- **Cap model**: Fast'n Easy Cap
- **Electrode type**: wet Ag/AgCl electrodes
- **Electrode material**: Ag/AgCl
- **Auxiliary channels**: EOG (1 ch)

## Participants

- **Number of subjects**: 10
- **Health status**: patients
- **Clinical population**: Healthy
- **Age**: mean=25.1, min=21, max=34
- **Gender distribution**: male=9, female=3
- **BCI experience**: mostly naive
- **Species**: human

## Experimental Protocol

- **Paradigm**: p300
- **Task type**: auditory ERP speller
- **Number of classes**: 2
- **Class labels**: Target, NonTarget
- **Tasks**: text spelling, counting task
- **Study design**: Nine-class auditory ERP paradigm with predictive text entry system (PASS2D). Users focus attention on two-dimensional auditory stimuli varying in pitch (high/medium/low) and direction (left/middle/right) presented via headphones.
- **Study domain**: communication
- **Feedback type**: visual
- **Stimulus type**: auditory tones
- **Stimulus modalities**: auditory, visual
- **Primary modality**: auditory
- **Synchronicity**: synchronous
- **Mode**: online
- **Training/test split**: True
- **Instructions**: Focus on target stimuli while ignoring all non-target stimuli. Minimize eye movements and muscle artifacts. Count targets during calibration. Spell sentences during online phase.

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  Target
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Target

  NonTarget
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Non-target

```
## Paradigm-Specific Parameters

- **Detected paradigm**: p300
- **Stimulus frequencies**: [708.0, 524.0, 380.0] Hz
- **Number of targets**: 9
- **Number of repetitions**: 15
- **Inter-stimulus interval**: 125.0 ms
- **Stimulus onset asynchrony**: 225.0 ms

## Data Structure

- **Trials**: 27
- **Trials context**: total across all calibration runs (3 runs × 9 trials per run)

## Preprocessing

- **Data state**: filtered and downsampled
- **Preprocessing applied**: True
- **Steps**: analog bandpass filter, lowpass filter, downsampling, artifact rejection
- **Highpass filter**: 0.1 Hz
- **Lowpass filter**: 40.0 Hz
- **Bandpass filter**: {'low_cutoff_hz': 0.1, 'high_cutoff_hz': 250.0}
- **Filter type**: analog bandpass then digital lowpass
- **Artifact methods**: threshold rejection
- **Re-reference**: nose
- **Downsampled to**: 100.0 Hz
- **Epoch window**: [-0.15, 0.8]
- **Notes**: Epochs with peak-to-peak voltage difference exceeding 100 μV in any channel were rejected during calibration. No artifact correction applied in online runs.

## Signal Processing

- **Classifiers**: FDA, Fisher discriminant analysis
- **Feature extraction**: mean amplitude in discriminative intervals
- **Spatial filters**: shrinkage regularization

## Cross-Validation

- **Method**: cross-validation
- **Evaluation type**: within_session

## Performance (Original Study)

- **Accuracy**: 72.5%
- **Itr**: 3.4 bits/min
- **Characters Per Minute**: 0.8
- **Spelling Speed Chars Per Min**: 0.8

## BCI Application

- **Applications**: speller, communication
- **Environment**: laboratory
- **Online feedback**: True

## Tags

- **Pathology**: Healthy
- **Modality**: Auditory
- **Type**: ERP, P300

## Documentation

- **Description**: A novel 9-class auditory ERP paradigm driving a predictive text entry system
- **DOI**: 10.3389/fnins.2011.00099
- **Associated paper DOI**: 10.3389/fnins.2011.00112
- **License**: CC-BY-NC-ND-4.0
- **Investigators**: Johannes Höhne, Martijn Schreuder, Benjamin Blankertz, Michael Tangermann
- **Senior author**: Michael Tangermann
- **Contact**: j.hoehne@tu-berlin.de
- **Institution**: Berlin Institute of Technology
- **Department**: Machine Learning Laboratory
- **Address**: Franklinstr. 28/19, 10587 Berlin, Germany
- **Country**: Germany
- **Repository**: BNCI Horizon
- **Publication year**: 2011
- **Keywords**: brain–computer interface, BCI, auditory ERP, P300, N200, spatial auditory stimuli, T9, user-centered design

## Abstract

Brain–computer interfaces (BCIs) based on event related potentials (ERPs) strive for offering communication pathways which are independent of muscle activity. While most visual ERP-based BCI paradigms require good control of the user's gaze direction, auditory BCI paradigms overcome this restriction. The present work proposes a novel approach using auditory evoked potentials for the example of a multiclass text spelling application. To control the ERP speller, BCI users focus their attention to two-dimensional auditory stimuli that vary in both, pitch (high/medium/low) and direction (left/middle/right) and that are presented via headphones. The resulting nine different control signals are exploited to drive a predictive text entry system. It enables the user to spell a letter by a single nine-class decision plus two additional decisions to confirm a spelled word. This paradigm – called PASS2D – was investigated in an online study with 12 healthy participants. Users spelled with more than 0.8 characters per minute on average (3.4 bits/min) which makes PASS2D a competitive method. It could enrich the toolbox of existing ERP paradigms for BCI end users like people with amyotrophic lateral sclerosis disease in a late stage.

## Methodology

Participants performed a single session lasting 3-4 hours consisting of calibration phase and online spelling task. Calibration: 3 runs (plus 1 practice run), each with 9 trials covering all 9 stimuli as targets. Each trial had 13-14 pseudo-random sequences of all 9 auditory stimuli (108 subtrials total, 12 target + 96 non-target). Online spelling: 2 runs spelling German sentences using T9-style predictive text system with 9-class decisions. Each trial consisted of 135 subtrials (15 iterations of 9 stimuli). Binary classification using linear FDA with shrinkage regularization on 2-4 amplitude values per channel from discriminative intervals (N200 at 230-300ms and P300 at 350+ ms). Multiclass decision based on one-sided t-test with unequal variances across 15 classifier outputs per key.

## References

Schreuder, M., Rost, T., & Tangermann, M. (2011). Listen, you are writing! Speeding up online spelling with a dynamic auditory BCI. Frontiers in neuroscience, 5, 112. https://doi.org/10.3389/fnins.2011.00112

Notes

.. versionadded:: 1.2.0
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
