# Blind Source Separation of Maternal and Fetal ECG using ICA

## Overview

This project implements **Blind Source Separation (BSS)** to separate independent biomedical signals from mixed ECG recordings. Specifically, it separates maternal ECG, fetal ECG, and noise from recordings captured by three ECG electrodes using **Independent Component Analysis (ICA)**.

## Problem Statement

During pregnancy, fetal monitoring is critical for ensuring maternal and fetal health. Standard ECG measurements typically capture a mixture of signals:
- **Maternal ECG**: The mother's heartbeat
- **Fetal ECG**: The baby's heartbeat
- **Noise**: Artifacts and environmental interference

The challenge is to extract clean, independent ECG signals from these mixed recordings using only the mixed sensor data—a problem known as Blind Source Separation.

## Solution Approach

This project uses **Independent Component Analysis (ICA)**, a statistical technique that:
1. Assumes the observed signals are linear mixtures of independent source signals
2. Finds statistically independent components that maximize non-Gaussianity
3. Recovers the original maternal ECG, fetal ECG, and noise components

### Algorithm
- **Method**: ICA (Independent Component Analysis)
- **Input**: 3 mixed ECG signals from electrode recordings
- **Output**: 3 separated independent components (maternal ECG, fetal ECG, noise)

## Project Structure

```
.
├── README.md                 # This file
├── notebooks/               # Jupyter notebooks for analysis and visualization
├── src/                      # Source code for ICA implementation
├── data/                     # Sample ECG data (if included)
└── results/                  # Output separated signals and visualizations
```

## Requirements

- Python 3.7+
- NumPy
- SciPy
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Installation

```bash
# Clone the repository
git clone https://github.com/yair-ytshaki/Blind_Source_Separation_of_maternal_and_fetal_ECG_using_ICA.git
cd Blind_Source_Separation_of_maternal_and_fetal_ECG_using_ICA

# Install dependencies
pip install -r requirements.txt
```

## Usage

Run the main Jupyter notebook to process ECG signals:

```bash
jupyter notebook
```

Navigate to the main analysis notebook to:
1. Load mixed ECG signals
2. Apply ICA decomposition
3. Visualize separated components
4. Analyze signal quality

## Results

The ICA algorithm successfully separates the mixed signals into:
- **Component 1**: Maternal ECG (typically higher frequency, regular rhythm)
- **Component 2**: Fetal ECG (typically lower amplitude, faster rhythm)
- **Component 3**: Noise/Artifacts

## Mathematical Background

### ICA Formulation
Given mixed signals **x** and unknown mixing matrix **A**:
```
x = A * s
```

Where **s** contains the independent source signals, ICA finds an unmixing matrix **W** such that:
```
y = W * x ≈ s
```

The algorithm maximizes statistical independence by optimizing a contrast function based on non-Gaussianity.

## References

- Hyvärinen, A., & Oja, E. (2000). Independent component analysis: algorithms and applications.
- Hyvarinen, A. (1999). Fast and robust fixed-point algorithms for independent component analysis.
- ECG signal processing and fetal monitoring literature

## License

This project is provided as-is for educational and research purposes.

## Author

**Yair Ytshaki**

## Contributing

Contributions, issues, and suggestions are welcome! Feel free to fork the repository and submit pull requests.

## Contact

For questions or collaboration inquiries, please open an issue on this repository.