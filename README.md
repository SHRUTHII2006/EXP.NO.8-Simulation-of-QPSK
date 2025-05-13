# EXP.NO.8-Simulation-of-QPSK

8.Simulation of QPSK

# AIM

To simulate Quadrature Phase Shift Keying (QPSK) modulation and demodulation using MATLAB,

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

![image](https://github.com/user-attachments/assets/70d4388b-74f4-47e1-8a73-68a73bd6a17c)


![image](https://github.com/user-attachments/assets/f6e9f9ad-9389-48ca-85f6-0990cce21564)


![image](https://github.com/user-attachments/assets/f9c310d7-6ef8-42be-88d8-cf818868d277)





# OUTPUT

![image](https://github.com/user-attachments/assets/c71d79a1-b2ea-4c0d-9c3d-a3bd11051aed)


 
# RESULT / CONCLUSIONS

The simulation of the QPSK modulation scheme was successfully performed using MATLAB. The modulated signal was transmitted over an AWGN channel, and the received signal was demodulated. The constellation diagram clearly displayed the four distinct QPSK states. The Bit Error Rate (BER) was calculated, and it was observed that the BER decreases as the Signal-to-Noise Ratio (SNR) increases, demonstrating the robustness of QPSK modulation in noisy environments.
