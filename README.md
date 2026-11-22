# Neural-to-Text EEG Decoding

A lightweight research prototype that maps short EEG windows to a **small set of speech/word classes**, then renders the predicted class as text. It includes a conventional neural baseline and a Leaky Integrate-and-Fire (LIF) spiking neural network (SNN) to explore neuromorphic-style temporal processing.

> **Research scope:** this is a constrained-vocabulary EEG decoding demonstration, not a general-purpose brain-to-text system. EEG does not directly contain clean word strings, and performance depends heavily on the recording paradigm, subject, preprocessing, and dataset quality.

## Why this project fits Neuromorphic AI Engineering

- Converts continuous EEG features into temporal spike trains.
- Implements a simple LIF spiking neuron model with membrane decay and threshold/reset.
- Compares a conventional ANN baseline with an SNN classifier.
- Reports accuracy, macro-F1, confusion matrix, and inference timing.
- Keeps the pipeline small enough to run on CPU; no GPU is required.

## Project structure

```text
neural-to-text-eeg-decoding/
├── notebooks/
│   └── neural_to_text_eeg_decoding.ipynb
├── data/
│   └── .gitkeep
├── results/
│   └── .gitkeep
├── README.md
├── CONTRIBUTING.md
├── CHANGELOG.md
├── LICENSE
├── requirements.txt
└── .gitignore
```

## Quick start

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate

python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```

Open `notebooks/neural_to_text_eeg_decoding.ipynb` and run all cells. The notebook starts with a clearly marked **synthetic demonstration dataset**, so the complete pipeline can be tested without downloading a large EEG corpus.

## Using real EEG data

The notebook accepts a prepared CSV file with:

- One row per trial/window.
- Numeric feature columns (for example band-power, channel statistics, or flattened time samples).
- A target column named `label` containing the associated word/utterance class.

Set `CSV_PATH` and `LABEL_COLUMN` in the real-data section. Keep subject/session identifiers out of the feature columns unless you intentionally want them included. Split by participant or recording session where possible to reduce data leakage.

Potential research datasets to investigate (check their current terms, access process, and citation requirements before use):

- **KARA ONE**: EEG and other physiological recordings for speech/phonological tasks; access may require registration or a research request.
- **ZuCo**: EEG recordings during natural reading; it is not a direct imagined-speech word-label dataset, so a different alignment/decoding task is needed.
- **MOABB-compatible EEG datasets**: useful for building and validating EEG preprocessing skills, but many are motor-imagery rather than speech datasets.

Do not assume that a dataset is plug-and-play. Confirm its task labels, sampling rate, channel layout, licensing, and subject-wise split protocol.

## Model pipeline

1. Load trial-level numeric EEG features and labels.
2. Standardize features using training data only.
3. Convert features to non-negative temporal input currents.
4. Encode currents as stochastic spike trains.
5. Train a LIF SNN classifier using surrogate gradients.
6. Compare with a small ANN baseline.
7. Decode the predicted class index into its text label.

## Important limitations

- This prototype predicts among labels represented in the training data; it does not generate arbitrary sentences.
- The synthetic data is only for checking that code runs. It is not evidence of EEG decoding performance.
- A scientifically meaningful result requires real, appropriately licensed EEG data and participant-independent evaluation.
- This is not a medical device and must not be used for diagnosis, treatment, or control of assistive equipment.

## Reproducibility

The notebook fixes random seeds and uses a stratified train/test split for the demo. For publication-quality evaluation, prefer grouped cross-validation by participant/session, report confidence intervals, and document all preprocessing choices.

## License

MIT. See [LICENSE](LICENSE).
