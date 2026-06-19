# qce26_qml_workshop

This repository supports the QCE26 workshop paper, **"Parity Learning with Small Quantum Neural Models."**

The project studies an unsupervised 16-bit even-parity generative benchmark. In this task, each data point is a 16-bit string, and the target distribution contains only bitstrings with an even number of 1s. The goal is to test whether different generative models can learn this global parity constraint from samples.

The models include:

* Local-window autoregressive MLP (AR-MLP)
* Masked causal autoregressive CNN (AR-CNN)
* Quantum Circuit Born Machine trained with a sample-based MMD loss (QCBM-MMD)

The goal is not to claim quantum advantage, but to use a small controlled benchmark to study how classical and quantum generative models behave when the target distribution contains a global constraint.

## Notebooks

1. `AR_MLP.ipynb`
   Implements the local-window autoregressive MLP baseline for the 16-bit even-parity distribution.

2. `AR_CNN.ipynb`
   Implements the masked causal autoregressive CNN baseline and evaluates different receptive-field settings.

3. `QCBM.ipynb`
   Implements the QCBM-MMD experiment using Qiskit and evaluates different circuit depths.

## Project Summary

This project compares classical autoregressive baselines and a QCBM-MMD model on an unsupervised even-parity distribution-learning task. The target distribution is uniform over 16-bit bitstrings with even parity. After training, each model generates new samples, which are evaluated using odd-parity violation rate, global parity expectation, and KL divergence.

Across the tested settings, the models remain close to parity-random generation. The QCBM-MMD loss decreases during optimization and its KL divergence improves with circuit depth, but the global even-parity constraint is not reliably learned.

This repository is intended to support reproducibility for the workshop paper.

## Citation

Citation information will be added after the workshop paper is accepted and the final conference/proceedings record is available.
