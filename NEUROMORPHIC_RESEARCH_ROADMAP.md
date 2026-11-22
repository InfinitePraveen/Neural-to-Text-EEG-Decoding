
# Neuromorphic AI Research Roadmap

## 1. Research Objective

The objective of this research roadmap is to evolve the Neural-to-Text EEG Decoding project into a real-world, low-power, neuromorphic Brain-Computer Interface (BCI) system.

The long-term goal is to investigate how Spiking Neural Networks (SNNs), EEG signal processing, and neuromorphic hardware can enable efficient neural communication.

---

## 2. Technologies to Explore

### Intel Loihi 2

**Category:** Neuromorphic Research Processor

Research objectives:
- Explore hardware-based Spiking Neural Networks.
- Implement Leaky Integrate-and-Fire (LIF) neuron models.
- Investigate event-driven computation.
- Benchmark neural inference latency.
- Evaluate energy efficiency against conventional neural networks.

Reference: https://www.intel.com/content/www/us/en/research/neuromorphic-computing.html

### BrainChip Akida

**Category:** Neuromorphic AI Processor

Research objectives:
- Explore event-based neural processing.
- Investigate low-power inference architectures.
- Study deployment of spiking neural networks.
- Evaluate edge AI applications.
- Investigate compatibility with neural signal processing workflows.

Reference: https://brainchip.com/

### MNE-Python

**Category:** EEG Signal Processing Framework

Research objectives:
- Load and process real EEG recordings.
- Perform EEG filtering and artifact removal.
- Implement epoch segmentation.
- Extract frequency-domain features.
- Analyze EEG signals across different participants.
- Prepare EEG features for SNN-based classification.

Reference: https://mne.tools/

---

## 3. Proposed Research Phases

### Phase 1: EEG Signal Processing
- Acquire appropriately licensed EEG datasets.
- Understand EEG channel configurations.
- Implement filtering and preprocessing.
- Extract relevant neural features.
- Establish reproducible preprocessing pipelines.

### Phase 2: Spiking Neural Networks
- Implement LIF neuron architectures.
- Experiment with rate-based spike encoding.
- Investigate temporal and latency-based encoding.
- Compare SNN and ANN classification performance.
- Study surrogate-gradient learning.

### Phase 3: Real-World EEG Decoding
- Replace synthetic data with real EEG recordings.
- Investigate speech-related EEG datasets.
- Develop constrained-vocabulary decoding.
- Evaluate participant-independent generalization.
- Analyze classification accuracy and Macro-F1.

### Phase 4: Neuromorphic Hardware Deployment
- Investigate Intel Loihi 2 research access.
- Explore BrainChip Akida development tools.
- Port compatible SNN architectures.
- Benchmark inference latency.
- Measure actual hardware energy consumption.
- Compare hardware performance with CPU-based inference.

### Phase 5: Brain-Computer Interface Integration
- Investigate real-time EEG acquisition.
- Develop streaming signal-processing pipelines.
- Implement low-latency neural inference.
- Explore real-time text output.
- Evaluate reliability, privacy, and user safety.

---

## 4. Performance Evaluation Metrics

| Metric | Research Purpose |
|---|---|
| Accuracy | Classification correctness |
| Macro-F1 | Balanced classification performance |
| Inference Latency | Neural processing speed |
| Spike Rate | Neural activity measurement |
| Energy Consumption | Hardware efficiency |
| Memory Usage | Deployment requirements |
| Subject Generalization | Cross-participant performance |

---

## 5. Research Datasets

Potential datasets to investigate:

- KARA ONE: EEG and physiological recordings for speech-related research.
- ZuCo: EEG recordings during natural reading.
- MOABB-compatible datasets: EEG benchmarking and signal-processing research.

Dataset selection must be based on task suitability, licensing, access requirements, and available annotations.

Note: These datasets do not all provide direct imagined-speech-to-word labels.

---

## 6. Expected Research Outcomes

The research aims to produce:

1. A reproducible EEG preprocessing pipeline.
2. An SNN-based neural classification architecture.
3. An ANN-versus-SNN performance comparison.
4. A constrained-vocabulary EEG-to-text decoding prototype.
5. A neuromorphic hardware deployment experiment.
6. A benchmark covering latency, accuracy, and energy consumption.
7. Technical documentation and open-source research contributions.

---

## 7. Long-Term Vision

Develop an efficient neuromorphic Brain-Computer Interface capable of translating appropriately acquired neural activity into text.

The broader research direction includes:
- Neuromorphic AI Engineering.
- Brain-Computer Interfaces.
- Event-driven AI architectures.
- Low-power edge intelligence.
- Neural signal processing.
- Human-computer interaction.

---

## 8. Responsible Research

EEG recordings contain sensitive personal information.

All experiments must:
- Follow informed-consent requirements.
- Respect dataset licenses and access conditions.
- Protect participant identities.
- Avoid unsupported claims about thought decoding.
- Clearly distinguish synthetic experiments from real-world results.
- Avoid medical or safety-critical deployment without appropriate validation and regulatory compliance.

---

**Research Focus:** Neural Signal Processing + Spiking Neural Networks + Neuromorphic Computing + Brain-Computer Interfaces.
