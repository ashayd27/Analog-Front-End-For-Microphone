# Passive Notch Filter – Signal Suppression at 50 Hz

This subproject demonstrates a **passive band-reject (notch) filter** designed to suppress a 50 Hz component from a composite input signal. The system is implemented in LTSpice using a twin-T resistor-capacitor network, and the results are verified through FFT analysis and waveform inspection.

---

## Filter Design Overview

- The **input** signal is a sum of **three sine waves**:
  - `17 V / 124 Hz`
  - `23 V / 83 Hz`
  - `8 V / 50 Hz` (target for suppression)
- These were **summed using an op-amp summer** circuit.
- The resulting composite signal was then passed through a **passive twin-T notch filter**, constructed using a combination of resistors and capacitors to target 50 Hz attenuation.
- An optional **non-inverting amplifier** using an op-amp was added after the twin-T network to restore the signal amplitude without affecting the filtering behavior.

---

## Files in This Folder

| File                              | Description                                                     |
|-----------------------------------|-----------------------------------------------------------------|
| `passive_input.png`               | Time-domain waveform of the input signal                        |
| `passive_output.png`              | Time-domain waveform of the filtered output                     |
| `passive_input_and_output.png`    | Input (blue) and output (green) signals overlaid for comparison |
| `passive_input_fft.png`           | FFT of input signal (showing all 3 frequency components)        |
| `passive_output_fft.png`          | FFT of output signal (notably suppressed 50 Hz peak)            |

---

## Results

- The **FFT analysis** (performed using LTSpice’s built-in FFT tool) confirms:
  - The **50 Hz** peak is attenuated by approximately 39 dB!
  - The other components at **83 Hz** and **124 Hz** remain largely unaffected
- This validates the notch filtering effectiveness of the passive twin-T network when tuned correctly to the interference frequency.

---

## Notes

- **Color coding in overlay:**
  - **Blue:** Input signal
  - **Green:** Output signal after notch filtering
- The twin-T design requires careful selection of resistor and capacitor values for precise notch frequency targeting.
- For signal chains requiring post-filter amplification, the output can be passed through an op-amp buffer or amplifier without affecting the filtering response.
