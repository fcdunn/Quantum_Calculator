# Quantum Calculator

A simple quantum computing demonstration using Qiskit. This project implements two quantum circuits capable of adding and multiplying integers encoded as qubits, using only CNOT, Toffoli, and P (phase change) gates. One is a "naive" version, the other is based on [Draper's construction](https://arxiv.org/pdf/quant-ph/0008033) and makes use of the Quantum Fourier Transform. Some very simple examples are given as demonstration.  

**Requirements**

The notebook runs on Python, using:
- Qiskit
- Numpy
- matplotlib and pylatexenc (for circuit drawing)
