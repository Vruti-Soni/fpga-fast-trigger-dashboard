# ⚡ Real-Time FPGA-Accelerated Trigger System (Hardware Emulation)

An interactive hardware-level emulation dashboard modeling a **CERN Level-1 Trigger (L1T)** and High-Speed Data Acquisition (DAQ) pipeline. Designed to visualize sub-nanosecond particle detector telemetry processing under the LHC's 40 MHz bunch crossing rate.

---

## 🔬 Physics & Hardware Architecture

At the Large Hadron Collider (LHC), experiments like ATLAS and CMS face an incoming collision rate of 40 million events per second. Because storing all raw telemetry is impossible, **hardware triggers** implemented on FPGAs (Field Programmable Gate Arrays) must make real-time Accept/Reject decisions in nanoseconds.

### 4-Stage FPGA Pipeline Architecture:
1. **Deserializer (SerDes):** Latches 16-channel differential LVDS detector hits at 1.6 Gbps (*1.2 ns latency*).
2. **DSP48E2 Amplitude Filter:** Compares pulse peak voltages against programmable transverse momentum ($p_T$) thresholds (*2.5 ns latency*).
3. **BRAM LUT Pattern Match:** Evaluates coordinate spatial topologies against pre-compiled trigger physics masks (*3.1 ns latency*).
4. **Decision Arbiter (L1A):** Asserts Level-1 Accept signals to front-end readout buffers (*0.8 ns latency*).

* **Total Pipeline Latency:** **7.6 ns** (well within strict LHC timing bounds).

---

## ✨ Key Features

* **Live Oscilloscope Telemetry:** Real-time canvas rendering of simulated analog particle detector voltage pulses and threshold discriminator cut lines ($V_{th}$).
* **Dynamic Hardware Registers:** Interactive sliders to adjust trigger thresholds and collision bunch rates on the fly.
* **Live Performance Metrics:** Tracks total collision events, L1 Accepts, deadtime loss, and sub-nanosecond hardware pipeline latency in real time.

Result(https://vruti-soni.github.io/fpga-fast-trigger-dashboard/)
