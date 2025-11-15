📘 Classical Data Encoding into Quantum States

Using Amplitude Encoding & Basis Encoding (Qiskit 1.3.1)

This repository demonstrates two essential techniques for encoding classical data into quantum states: Amplitude Encoding and Basis Encoding. These approaches are fundamental in quantum computing applications such as quantum machine learning, optimization, and data processing.

Both examples in this repository show how to:
	•	Construct a valid quantum state vector
	•	Normalize classical data according to quantum constraints
	•	Convert the state vector into a quantum circuit
	•	Transpile the circuit into hardware-compatible elementary gates

├── amplitude_encoding_example.py

├── basis_encoding_example.py

└── README.md


1. Amplitude Encoding

🧠 What Is Amplitude Encoding?

Amplitude encoding embeds classical numerical data directly into the amplitudes of a quantum state:

<img width="185" height="66" alt="Screenshot 2025-11-15 at 4 56 21 PM" src="https://github.com/user-attachments/assets/f739f2c2-34e8-41ba-915a-372dff525520" />


Where each amplitude a_i comes from normalized classical data.

⭐ Why Amplitude Encoding?
	•	Highly efficient representation: encodes 2^n classical values using only n qubits
	•	Suitable for numerical datasets (features, time series, probability distributions)
	•	Enables compact embedding of high-dimensional vectors

  What the Code Does

✔ Step 1 — Prepare Classical Data
	•	Dataset: [2, 7, 6, 2, 5]
	•	Padded to next power of 2 (size 8)
	•	Normalized to satisfy quantum state requirements

✔ Step 2 — Build the Quantum State

prepare_state() generates a quantum circuit whose final state matches the constructed state vector.


Step 3 — Transpile to Supported Gates

basis_gates = ['u1', 'u2', 'u3', 'cx']

eal-World Applications of Amplitude Encoding
	•	Quantum Machine Learning
(Quantum Neural Networks, QSVM, Quantum Feature Maps)
	•	Quantum Finance
Portfolio vectors, risk models, covariance matrices
	•	Quantum Signal Processing & Compression
	•	High-dimensional data embedding
Used widely when the input data consists of continuous values.


2. Basis Encoding

🧠 What Is Basis Encoding?

Basis encoding maps classical bitstrings directly into quantum computational basis states.

<img width="405" height="139" alt="Screenshot 2025-11-15 at 4 57 56 PM" src="https://github.com/user-attachments/assets/fd8cb033-8e63-46ee-8856-1dd601e35910" />

What the Code Does

✔ Step 1 — Define Bitstrings

Bitstrings chosen:
"0101"
"1011"

Their indices in a 4-qubit state vector (size 16) are set to amplitude 1.

✔ Step 2 — Normalize the State

Even binary state vectors must be normalized.

✔ Step 3 — Generate the Circuit

prepare_state() constructs the exact quantum state.

✔ Step 4 — Transpile Using Rotation Gates
basis_gates = ['rx', 'ry', 'rz', 'cx']

	
	•	Grover’s Algorithm (Quantum Search)
Marking specific basis states.
	•	Quantum Cryptography
Keys and classical bit sequences represented as qubit basis states.
	•	Quantum Error Correction
Error syndromes and codewords use basis representations.
	•	QAOA (Quantum Approximate Optimization Algorithm)
Binary variables (0/1 decisions) map naturally to basis states.

