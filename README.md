# Shor-s-Algorithm-
Implementation of Shor's Algorithm to factor a number using Qiskit. 

Shor's algorithm can be used to factor numbers $N$ that are products of the form 

$$N = pq$$

where $p$ and $q$ are prime numbers. We will use two registers of qubits. The first register will have $n$ qubits, and will contain the measurement qubits. The second register will have $m$ qubits, and will be the eigenstate for quantum phase estimation.

1. Initializing our qubits: We create a superposition of all $2^n$ computational basis states on the $n$ measurement qubits by applying a Hadamard ( $H$ ) gate on each qubit starting off in the state $\vert0\rangle^{\otimes n}$. We also initialize the $m$ target qubits in the state $\vert1\rangle$. Here, the exponent $\otimes n$ means that we have a tensor product of the states of $n$ qubits.

2. We apply the unitary operator $U$ with various powers onto the target qubits by controlling it with each of the different measurement qubits. The unitary operator in this case implements modular exponentiation. 

3. We apply an inverse quantum Fourier transform on the $n$ measurement qubits.

4. Measuring the first $n$ qubits. 

After the measurement outcomes are determined, we will need to do additional classical post-processing in order to determine the factors


Reference: Qiskit Summer School 
