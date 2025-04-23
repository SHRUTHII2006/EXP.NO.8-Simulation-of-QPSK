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

![qpsk 1](https://github.com/user-attachments/assets/f0069491-b1fa-4e36-b6f6-582044e71736)

![qpsk 2](https://github.com/user-attachments/assets/4736cf2a-0200-4f65-93b4-c782e20ef007)


# OUTPUT

![image](https://github.com/user-attachments/assets/0733fa83-5ff9-4822-9252-1a6d50fe1004)

 
# RESULT / CONCLUSIONS

The simulation of the QPSK modulation scheme was successfully performed using MATLAB. The modulated signal was transmitted over an AWGN channel, and the received signal was demodulated. The constellation diagram clearly displayed the four distinct QPSK states. The Bit Error Rate (BER) was calculated, and it was observed that the BER decreases as the Signal-to-Noise Ratio (SNR) increases, demonstrating the robustness of QPSK modulation in noisy environments.
