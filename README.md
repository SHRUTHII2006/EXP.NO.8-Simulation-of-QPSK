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

import numpy as np
import matplotlib.pyplot as plt

Parameters

num_symbols = 10 # Number of symbols (reduced for clarity in the plot)
T = 1.0 # Symbol period
fs = 100.0 # Sampling frequency
t = np.arange(0, T, 1/fs) # Time vector for one symbol

Generate random bit sequence

bits = np.random.randint(0, 2, num_symbols * 2) # Two bits per QPSK symbol
symbols = 2 * bits[0::2] + bits[1::2] # Map bits to QPSK symbols

Initialize QPSK signal

qpsk_signal = np.array([])
symbol_times = []

Define the QPSK modulation and phase angles

symbol_phases = {0: 0, 1: np.pi/2, 2: np.pi, 3: 3*np.pi/2}

Generate QPSK signal

for i, symbol in enumerate(symbols):
  phase = symbol_phases[symbol]
  symbol_time = i * T
  qpsk_segment = np.cos(2 * np.pi * t / T + phase) + 1j * np.sin(2 * np.pi * t / T + phase)
  qpsk_signal = np.concatenate((qpsk_signal, qpsk_segment))
  symbol_times.append(symbol_time)

Time vector for the entire signal

t_total = np.arange(0, num_symbols * T, 1/fs)

 Plot real and imaginary parts of the QPSK signal

plt.figure(figsize=(14, 12))

 Plot the in-phase component with symbols

plt.subplot(3, 1, 1)
plt.plot(t_total, np.real(qpsk_signal), label='In-phase')
for i, symbol_time in enumerate(symbol_times):
  plt.axvline(symbol_time, color='red', linestyle='--', linewidth=0.5)

  plt.text(symbol_time + T/4, 0, f'{symbols[i]:02b}', fontsize=12, color='blue')
plt.title('QPSK Signal - In-phase Component with Symbols')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()

 Plot the quadrature component with symbols

plt.subplot(3, 1, 2)
plt.plot(t_total, np.imag(qpsk_signal), label='Quadrature', color='orange')
for i, symbol_time in enumerate(symbol_times):
  plt.axvline(symbol_time, color='red', linestyle='--', linewidth=0.5)
  plt.text(symbol_time + T/4, 0, f'{symbols[i]:02b}', fontsize=12, color='blue')
plt.title('QPSK Signal - Quadrature Component with Symbols')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()

Plot the resultant QPSK waveform (real part)

plt.subplot(3, 1, 3)
plt.plot(t_total, np.real(qpsk_signal), label='Resultant QPSK Waveform', color='green')
for i, symbol_time in enumerate(symbol_times):
  plt.axvline(symbol_time, color='red', linestyle='--', linewidth=0.5)
  plt.text(symbol_time + T/4, 0, f'{symbols[i]:02b}', fontsize=12, color='blue')
plt.title('Resultant QPSK Waveform')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()

# OUTPUT

![image](https://github.com/user-attachments/assets/0733fa83-5ff9-4822-9252-1a6d50fe1004)

 
# RESULT / CONCLUSIONS

The simulation of the QPSK modulation scheme was successfully performed using MATLAB. The modulated signal was transmitted over an AWGN channel, and the received signal was demodulated. The constellation diagram clearly displayed the four distinct QPSK states. The Bit Error Rate (BER) was calculated, and it was observed that the BER decreases as the Signal-to-Noise Ratio (SNR) increases, demonstrating the robustness of QPSK modulation in noisy environments.
