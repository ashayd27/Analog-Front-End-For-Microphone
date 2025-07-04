# Noise-Reducing Analog Front-End for Microphone Circuits

This project implements and compares **passive** and **active** analog notch filters to suppress **50 Hz power line interference** in microphone circuits—while preserving **speech intelligibility**. Designed and simulated in **LTSpice**, this front-end is achieving up to 32 dB noise attenuation. This repository includes schematics, FFT analysis, and filter comparision.

---

## Problem Statement

Low-frequency hum (especially at **50 Hz** from AC mains) pollutes microphone signals in embedded setups. Software-based filtering adds latency and power consumption. This project aims to eliminate that noise **before ADC conversion**, using **pure analog signal conditioning**.

---

## Features

- **Twin-T Passive Notch Filter**: Simple, cost-effective topology  
- **Op-Amp Based Active Notch Filter**: Combination of a low pass and high pass filter in parallel 
- **Simulation in LTSpice** with FFT analysis and frequency response plots  
- Preserves speech signal while suppressing low-frequency hum (~39 dB)

---

## Components & Tools

- **Software:** LTSpice XVII  
- **Filters Designed:**  
  - Passive: Twin-T notch filter  
  - Active: Op-amp-based notch filter (based on LM741/LM324 equivalents)  
- **Simulation Tools:** FFT, transient response, frequency sweep

