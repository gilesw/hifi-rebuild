
# 2 channel room correction

CamillaDSP and CamillaFIR on linux

# movies

kodi permanently directed to hdmi out


# diagram
```
LINUX PC (The Source)
  │
  ├──[USB Cable]──▶ DENAFRIPS DAC ──────┐
  │                                     │ (Analog Music Path)
  └──[HDMI Cable]─▶ MARANTZ AV 30 ──────┼───────┐
                    (Front L/R Out)     │       │
                          │             │       │ (Analog Movie Path)
                          ▼             ▼       │
                  ┌───────────────────────┐     │
                  │ MUSICAL FIDELITY PRE  │     │
                  │ (The Selector Switch) │     │
                  └──────────┬────────────┘     │
                             │                  │
                             ▼                  ▼
                    ┌────────────────┐  ┌────────────────┐
                    │ NORD MONO AMPS │  │ NORD 3-CH AMP  │
                    │  (Front L/R)   │  │ (C / SL / SR)  │
                    └────────┬───────┘  └────────┬───────┘
                             │                   │
                    ┌────────▼────────┐ ┌────────▼────────┐
                    │ RIBBON TOWERS   │ │ CENTER/SURROUND │
                    └─────────────────┘ └─────────────────┘
```

# System Blueprint: High-Fidelity Hybrid Home Theater (2026)

## 1. Executive Summary
A dual-purpose system designed to deliver an uncompromising, organic 2-channel R-2R musical experience while providing a seamless, Dirac-corrected 5.1 cinematic environment. The architecture uses a **"Dual-Brain"** approach where a dedicated Analog Preamplifier manages the front-stage power, allowing the Home Theater Processor to act as a slave for cinema and remain powered down for music.

---

## 2. Hardware Manifest

### 2.1 The "Brains" (Processors & DACs)
* **Stereo DAC:** Denafrips Pontus 15th (R-2R Ladder DAC).
* **Analog Preamp:** Musical Fidelity M6s PRE (Class A, Fully Balanced).
    * **Role:** Master analog controller and volume for music.
    * **Key Feature:** **BALANCED 1** input configured for **HT Bypass** via rear toggle.
* **AV Processor:** Marantz AV 30 (11.4 Channel / Dirac Live ART).
    * **Role:** Digital decoding, HDMI switching (1080p fixed for Epson), and Dirac ART management.

### 2.2 The "Muscle" (Amplification)
* **Front Stage (L/C/R):** Nord One NCx500 3-Channel MKII.
    * **Buffer:** Nord Rev D Input Buffer with **Sparkos Labs SS2590** Op-Amps (adds Class A/B warmth).
* **Surrounds (LS/RS):** Existing NCore Mono Blocks (repurposed for rear channels).
* **Subwoofer:** REL HT/1205 (Active/Self-Powered).

### 2.3 Visuals
* **Projector:** Epson EH-TW5910 (1080p).
* **Connectivity:** 8K Active Optical Cable (AOC) HDMI (to ensure 1080p stability over distance).

---

## 3. Signal Chain & Logic

### 3.1 2-Channel Music (The "Purist" Loop)
1. **Source:** Linux PC (Ubuntu Jammy) → **USB** → Denafrips Pontus.
2. **DSP:** CamillaDSP (FIR filters) applied on PC before the DAC.
3. **Preamp:** Denafrips (XLR) → **MF M6s PRE (Balanced 2)**.
4. **Power:** MF M6s PRE (XLR Out) → **Nord 3-Ch Amp (Ch 1 & 2)** → Ribbon Towers.

### 3.2 5.1 Movie Path (The "Cinematic" Loop)
1. **Source:** Linux PC (Kodi/VLC) → **HDMI** → Marantz AV 30.
2. **Video:** Marantz → **AOC HDMI (1080p Fixed)** → Epson Projector.
3. **Front L/R:** Marantz (Front XLR Pre-Out) → **MF M6s PRE (Balanced 1/HT)** → Nord Amp (Ch 1 & 2).
4. **Center:** Marantz (Center XLR Pre-Out) → **Nord 3-Ch Amp (Ch 3)**.
5. **Surrounds:** Marantz (Surround XLR Pre-Out) → **NCore Mono Blocks**.
6. **Subwoofer:** Marantz (Sub 1 Out) → **REL Sub (Direct)**.

---

## 4. Automation: 12V Trigger Logic
All power is managed by the **Marantz AV 30** "Trigger Assignments" to allow selective power-on.

| Trigger Out | Destination | Music Mode | Movie Mode |
| :--- | :--- | :--- | :--- |
| **Trigger 1** | Nord 3-Ch (Fronts) | **ON** | **ON** |
| **Trigger 2** | NCore Monos (Rears) | **OFF** | **ON** |
| **Trigger 3** | MF Preamp (via Relay) | **ON** | **ON** |

*Note: The Musical Fidelity requires a 12V Trigger-to-AC Relay box as it lacks a native trigger input.*

---

## 5. System Diagram (Mermaid)

```mermaid
graph TD
    PC[Linux PC] -- USB --> DAC[Denafrips Pontus]
    PC -- HDMI --> AVP[Marantz AV 30]
    
    DAC -- XLR --> MF[MF M6s PRE]
    AVP -- "XLR (Front L/R)" --> MF
    
    MF -- XLR --> Amp1[Nord 3-Ch - Ch 1&2]
    AVP -- "XLR (Center)" --> Amp1
    AVP -- "XLR (Surrounds)" --> Amp2[NCore Monos]
    AVP -- "LFE" --> Sub[REL Active Sub]

    Amp1 --> Speakers[Ribbon L/C/R]
    Amp2 --> RearSpeakers[Surrounds]
    AVP --> Proj[Epson Projector]

    style MF fill:#f96,stroke:#333,stroke-width:2px
    style AVP fill:#ccf,stroke:#333
