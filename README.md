# EXP.NO.8-Simulation-of-QPSK

8.Simulation of QPSK

# AIM

# SOFTWARE REQUIRED

Python Software

-> Numpy Library

-> Matplotlib Library

-> Scipy Library (for signal processing)

# ALGORITHMS

1. Generate Random Data:
Generate a binary sequence (0s and 1s) which will be used as the input data.

2. Group Bits into Symbols:
QPSK maps 2 bits per symbol:

00 → π/4

01 → 3π/4

11 → 5π/4

10 → 7π/4

3. Modulate Using QPSK:
Use the formula:
𝑠(𝑡)=2𝐸𝑏𝑇cos⁡(2𝜋𝑓𝑐𝑡+𝜙)
s(t)=T2E bcos(2πfct+ϕ)

where,
ϕ depends on bit pair.

5. Add AWGN (Optional):
Add Gaussian noise using MATLAB’s awgn() function to simulate real-world conditions.

6. Demodulate QPSK Signal:
Extract phase information and convert back to binary pairs.

7. Calculate BER (Bit Error Rate):
Compare the transmitted and received bits.

# PROGRAM

# OUTPUT
 
# RESULT / CONCLUSIONS
