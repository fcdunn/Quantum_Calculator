# Quantum Calculator

A simple quantum computing demonstration using Qiskit. This project implements two quantum circuits capable of adding and multiplying integers encoded as qubits, using only CNOT, Toffoli, and P (phase change) gates. One is a "naive" version, the other is based on [Draper's construction](https://arxiv.org/pdf/quant-ph/0008033) and makes use of the Quantum Fourier Transform. Some very simple examples are given as demonstration.  

**Requirements**

The notebook runs on Python, using:
- Qiskit
- Numpy
- matplotlib and pylatexenc (for circuit drawing)


**Example Calculation**

Below is a simple example, using (the matrix for) the "naive" calculator circuit to compute $1 \times 1 = 1$.

```python
from qiskit.quantum_info import Operator
import numpy as np

from Quantum_Calculator import QCALC

# QCALC(d) creates the circuit for addition or multiplication on numbers encoded by up to d qubits.
# For ease of computing/demonstration in small examples, we use the unitary matrix associated to the circuit.
QCALC_matrix = Operator(QCALC(1))

# We choose this particular start_vector to indicate the two inputs 1 and 1, and that they should be multiplied together.
start_vector = np.zeros(2**6)
start_vector[7] = 1 
start_vector.reshape(-1,1)

# The end_vector in this case is zero except a single entry 1 at index 15, corresponding to inputs remaining the same, and the output qubits encoding 1.
end_vector = np.matmul(QCALC_matrix, start_vector)
print(end_vector)
```


