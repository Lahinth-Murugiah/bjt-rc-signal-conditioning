# Analog Signal Conditioning with a BJT and RC Filters

A 9 V analog signal-conditioning prototype for the recovered audio in a simple AM receiver. The circuit combines input high-pass filtering, common-emitter voltage amplification, and output low-pass filtering. It was simulated in Proteus and built on both breadboard and Dot Board for **IE2034 Analog Electronics, Group 11**.

[Final assignment report](docs/analog-electronics-final-report.pdf) · [Proteus waveform capture](simulation/proteus-waveforms.png) · [Lab oscilloscope capture](measurements/oscilloscope-5khz.jpg)

## Circuit design

![Proteus schematic showing the 9 V common-emitter amplifier and RC networks](simulation/proteus-schematic.png)

| Circuit function | Components shown in Proteus | Design intent |
| --- | --- | --- |
| Input coupling and high-pass response | C1 = 10 nF, R1 = 47 kΩ, R2 = 8.2 kΩ | Nominal lower cutoff near 2 kHz |
| Common-emitter amplifier | Q1 = 2N3904, R3 = 4.7 kΩ, R4 = 1 kΩ, C3 = 100 µF | Invert and amplify the signal from a 9 V supply, with a midband gain target of at least 60 V/V |
| Output coupling and low-pass response | C2 = 10 µF, R5 = 8.8 kΩ, C4 = 1.5 nF | Block the collector DC level and target an upper cutoff near 12 kHz |

Using the report's simplified RC calculation, C1 with R2 gives approximately **1.94 kHz** and R5 with C4 gives approximately **12.06 kHz**. The actual cutoff frequencies depend on the impedances driving and loading each network. The component table follows the Proteus schematic. The report's amplifier description names a 2N2222, while the schematic labels Q1 as 2N3904.

## Simulation and bench results

The [Proteus oscilloscope capture](simulation/proteus-waveforms.png) shows the input and output traces at a generator setting of about 10.1 kHz and 101 mV peak-to-peak.

For the bench capture, the [function generator](measurements/function-generator-5khz.jpg) was set to a 5 kHz sine wave at 100 mV peak-to-peak, with zero DC offset. The [oscilloscope](measurements/oscilloscope-5khz.jpg) shows 128 mV peak-to-peak on the input and 6.20 V peak-to-peak on the output. The ratio is **48.4 V/V** using the scope readings or **62 V/V** using the generator setting. The output trace visibly clips, so both ratios describe this capture. The supplied capture does not establish the linear small-signal gain or the measured cutoff frequencies.

## Hardware prototypes

| Breadboard | Dot Board |
| --- | --- |
| [![Breadboard prototype with transistor, resistors, capacitors, and test leads](hardware/breadboard-prototype.jpg)](hardware/breadboard-prototype.jpg) | [![Soldered Dot Board prototype viewed from the component side](hardware/dot-board-prototype.jpg)](hardware/dot-board-prototype.jpg) |

## Repository contents

| Path | Contents |
| --- | --- |
| [docs/](docs/) | Group 11 final assignment report with student IDs removed |
| [simulation/](simulation/) | Proteus circuit schematic and waveform screenshots |
| [hardware/](hardware/) | Breadboard and Dot Board prototype photos |
| [measurements/](measurements/) | Function generator settings and oscilloscope capture from the 5 kHz bench test |

**Project team** · Viyashan K. and Lahinth M.
