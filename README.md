# Phase-Locked Loop (PLL)

![Technology](https://img.shields.io/badge/Technology-180nm%20TSMC-green)
![Tool](https://img.shields.io/badge/Tool-Cadence%20Virtuoso-blue)
![Simulator](https://img.shields.io/badge/Simulator-ADE%20L%20Spectre-orange)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

A **Phase-Locked Loop (PLL)** being designed and simulated in Cadence Virtuoso using TSMC 180nm technology. Currently, the **Phase Frequency Detector (PFD)** and **Voltage Controlled Oscillator (VCO)** blocks have been designed and simulated. Charge Pump, Loop Filter, and Frequency Synthesizer are in progress.

---

## Specifications

| Parameter | Value |
|-----------|-------|
| Supply Voltage (VDD) | 1.8V |
| Center Frequency | 2.75 GHz |
| Usable Frequency Range | 2.5 GHz – 3 GHz |
| Divider Ratio (N) | 32 |
| VCO Gain (Kvco) | 5 GHz/V |
| Loop Bandwidth | 5 – 8 MHz |
| Reference Frequency | 87.5 MHz |
| Technology Node | 180nm TSMC |
| Simulator | Spectre (ADE L) |
| VCO Type | 3-Stage Ring Oscillator |

---

## PLL Architecture

A complete PLL consists of the following blocks:

```
Ref Clock ──► PFD ──► Charge Pump ──► Loop Filter ──► VCO ──► Output
                                                         │
                                          Divider ◄──────┘
```

| Block | Status |
|-------|--------|
| Phase Frequency Detector (PFD) | ✅ Complete |
| Voltage Controlled Oscillator (VCO) | ✅ Complete |
| Charge Pump (CP) | 🔄 In Progress |
| Loop Filter (LPF) | 🔄 In Progress |
| Frequency Synthesizer / Divider | 🔄 In Progress |



## Design Notes

- **PFD** implemented using two D flip-flops with a reset path to generate UP/DN signals
- **VCO** implemented as a **3-stage ring oscillator** — simple topology suitable for moderate frequency ranges at 180nm
- Ring oscillator chosen for ease of integration and low design complexity at this stage
- Full PLL integration with CP, LPF, and divider is currently in progress
- Simulated using **Spectre** via **ADE L** in Cadence Virtuoso

---

## Future Work

- [ ] Design and simulate Charge Pump (CP)
- [ ] Design Loop Filter (LPF) for stability
- [ ] Implement Frequency Divider
- [ ] Full PLL integration and lock acquisition simulation
- [ ] VCO tuning curve (Frequency vs Vctrl)
- [ ] Phase noise analysis
