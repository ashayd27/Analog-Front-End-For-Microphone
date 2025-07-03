# Active Notch Filter – Signal Suppression at 50 Hz

This subproject demonstrates a **passive band-reject (notch) filter** designed to suppress a 50 Hz component from a composite input signal. The system is implemented in LTSpice using op-amp-based filter blocks and verified through FFT analysis and waveform inspection.

---

## 🔧 Filter Design Overview

- The **input** signal is a sum of **three sine waves**:
  - `17 V / 124 Hz`
  - `23 V / 83 Hz`
  - `8 V / 50 Hz` *(target for suppression)*
- These were **summed using an op-amp adder** circuit.
- The resulting composite signal was then passed through a twin T **passive notch filter**, consisting of:
  - A **low-pass filter** and a **high-pass filter**, each implemented using op-amps to create the notch filter behaviour
  - Their outputs were fed into another **op-amp adder** to add up the waveforms from the two filters
- The **output gain** of the final adder stage can be fine-tuned by adjusting resistor values to prevent amplitude clipping or excessive attenuation.

---

## Files in This Folder

| File                              | Description                                                     |
|-----------------------------------|-----------------------------------------------------------------|
| `active_input.png`                | Time-domain waveform of the input signal                        |
| `active_output.png`               | Time-domain waveform of the filtered output                     |
| `active_input_and_output.png`     | Input (blue) and output (green) signals overlaid for comparison |
| `active_input_fft.png`            | FFT of input signal (showing all 3 frequency components)        |
| `active_output_fft.png`           | FFT of output signal (notably suppressed 50 Hz peak)            |

---

## Results

- The **FFT analysis** (performed using LTSpice’s built-in FFT tool) confirms:
  - **124 Hz** and **83 Hz** components remain intact
  - The **50 Hz component** is **attenuated by approximately 12 dB**
- This validates the effective band-rejection behavior of the active notch configuration, specifically tuned for 50 Hz interference.

---

## Notes

- **Color coding in overlay:**  
  - **Blue:** Input signal  
  - **Green:** Output signal after notch filtering  
