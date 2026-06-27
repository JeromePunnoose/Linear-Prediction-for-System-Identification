
# Linear Prediction Based Speech Analysis and Synthesis

A complete implementation of **Linear Predictive Coding (LPC)** for speech analysis and synthesis, including direct-form and lattice-form realizations, Levinson-Durbin recursion, and system identification using linear prediction.

---

## Overview

This project demonstrates how linear prediction can be used to model speech signals and reconstruct them efficiently. It covers the complete workflow from autocorrelation computation to lattice filter implementation and speech reconstruction.

The project also investigates the decorrelation and reconstruction properties of lattice filters and explores system identification using LPC techniques.

---

## Features

- Linear Predictive Coding (LPC)
- Autocorrelation method
- Levinson-Durbin recursion
- Direct-form LPC analyzer
- Direct-form LPC synthesizer
- Analysis lattice filter
- Synthesis lattice filter
- Reflection coefficient computation
- Prediction error analysis
- Correlation analysis at each lattice stage
- System identification using linear prediction
- Python-based simulations and visualizations

---

## Project Structure

```
Linear-Prediction-Speech-Analysis/
│
├── data/
│   ├── input_speech.wav
│   └── output_speech.wav
│
├── src/
│   ├── analyzer.py
│   ├── synthesizer.py
│   ├── levinson.py
│   ├── lattice_filter.py
│   ├── autocorrelation.py
│   ├── system_identification.py
│   └── utils.py
│
├── figures/
│
├── report/
│   └── Project_Report.pdf
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Theory

### Linear Prediction

A speech sample is predicted from previous samples as

\[
\hat{x}(n)=\sum_{k=1}^{p}a_kx(n-k)
\]

where

- \(a_k\) are the LPC coefficients
- \(p\) is the prediction order

The prediction error is

\[
e(n)=x(n)-\hat{x}(n)
\]

---

### Autocorrelation Method

The autocorrelation sequence is computed as

\[
R(k)=\sum_{n}x(n)x(n-k)
\]

The LPC coefficients are obtained by solving the Yule-Walker equations.

---

### Levinson-Durbin Recursion

The Levinson-Durbin algorithm efficiently computes

- LPC coefficients
- Reflection coefficients
- Prediction error energy

with computational complexity

\[
O(p^2)
\]

instead of

\[
O(p^3)
\]

---

### Lattice Filters

The project implements

- Analysis lattice filter
- Synthesis lattice filter

using reflection coefficients.

The forward prediction error is

\[
e_m^{+}(n)=e_{m-1}^{+}(n)+k_me_{m-1}^{-}(n-1)
\]

The backward prediction error is

\[
e_m^{-}(n)=e_{m-1}^{-}(n-1)+k_me_{m-1}^{+}(n)
\]

where

- \(k_m\) is the reflection coefficient of stage \(m\).

---

## System Identification

The project demonstrates how an unknown linear system can be identified by

1. Exciting the system using an input signal
2. Recording the system output
3. Estimating the LPC model
4. Recovering the system coefficients
5. Comparing the estimated model with the original system

---

## Simulation Results

The project includes

- Input speech waveform
- Output speech waveform
- LPC spectrum
- Prediction error signal
- Autocorrelation plots
- Reflection coefficients
- Lattice stage outputs
- Correlation at each lattice stage
- Frequency response
- Pole-zero plots
- System identification results

---

## Technologies Used

- Python
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook

---

## Future Improvements

- Real-time speech analysis
- LPC vocoder implementation
- Adaptive lattice filters
- Noise reduction
- Higher-order prediction models
- Real-time audio interface
- Deep learning comparison

---

## References

1. J. Makhoul, "Linear Prediction: A Tutorial Review," Proceedings of the IEEE, 1975.

2. L. R. Rabiner and R. W. Schafer, *Digital Processing of Speech Signals*.

3. S. Haykin, *Adaptive Filter Theory*.

4. A. V. Oppenheim and R. W. Schafer, *Discrete-Time Signal Processing*.

---

## Author

**Jerome Punnoose**

Department of Electronics and Communication Engineering

Project: **Linear Prediction Based Speech Analysis and Synthesis**

---

## License

This project is intended for educational and research purposes.
