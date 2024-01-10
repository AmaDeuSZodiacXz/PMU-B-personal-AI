# Deep Learning for Sleep State Scoring

## Introduction
This project leverages deep learning to analyze bio-signals, such as brain waves and heartbeats, for sleep state scoring. Key motivations include addressing sleep disorders like insomnia and sleep apnea. Traditional approaches rely on patient-reported symptoms, but these often fall short in pinpointing specific causes and effective treatments. The project aims to streamline the process by eliminating the need for hospital stays, using deep learning to interpret overnight bio-signal data.

## Bio-signal Techniques
Noise removal in preprocessing and expert-driven feature extraction, termed "hands-engineering," are critical. These steps require deep domain knowledge, but deep learning offers a potential bypass.

## Case Study: Sleep State Scoring
- **Objective**: Improve sleep efficiency.
- **Method**: Use Polysomnogram (PSG) to collect data (EEG, EOG, ECG, EMG) during 8-hour sleep sessions across several days.
- **Sleep Stages**: 
  - Non-REM (N1: onset, N2: light, N3: deep sleep)
  - REM (rapid eye movement, associated with dreaming)
  - W (awake)
- **Cycle Patterns**: Sleep typically cycles between non-REM and REM stages, with longer, deeper REM phases closer to waking up.

### Neuroscience Context
- **REM Stage**: Characterized by stable brain waves but erratic eye movements.
- **Sleep Evaluation**: Employs domain knowledge like identifying simultaneous brain and eye activity in the N2 stage.

### Scoring Criteria
- Total Sleep Time (TST), Time in Bed (TIB), etc., with formulas like Sleep Efficiency = (TST/TIB) * 100.

## Modeling with Deep Learning
- **Dataset**: Accessible at [Physionet](https://physionet.org/content/sleep-edfx/1.0.0/).
- **Models**: Evolution from Deep Sleep Net (2017) to Tiny Sleep Net (2020).
- **Deep Sleep Net Architecture**: Combines 1D-CNN with bidirectional LSTM, incorporating Fourier transform concepts and RESNet architecture.

### Tiny Sleep Net Modifications
- Simplified 1D-CNN branch, fewer sequential learning layers.
- Switch from bidirectional to unidirectional LSTM.
- Data augmentation techniques for training.

## Evaluation
- **Method**: k-fold cross-validation.
- **Criteria**: Focus on maximizing Recall to effectively identify sleep issues.
- **Visualization**: Hypnograms to represent sleep states.

## Workshop
- **Simple Model Implementation**: A basic neural network model in Python.
- **Training Challenges**: Issues with class N1 performance, highlighting the need for sequential learning and balanced loss functions.

