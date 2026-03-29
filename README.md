# System Blueprint: The Transmission Line Purist (v8.0)

## 1. Project Vision
A 2026 consolidation project: Replacing high-heat legacy DIY amplification with a high-efficiency Purifi/Marantz core. Optimized for a 37m³ narrow room, prioritizing the "speed" of IPL Ribbon tweeters and the low-end extension of Transmission Line towers.

---

## 2. Hardware Manifest

### 2.1 The "Front Stage" (IPL Heritage)
* **Main Towers:** IPL S2TLM (Transmission Line).
    * **Drivers:** 8" Kevlar (IPL/8/K) + Fountek Neo CD3.0 Ribbon.
    * **Note:** 23Hz extension allows for sub-free 2.0 music listening.
* **Center:** IPL AVC-PRO (Acoustic Vent Centre).
    * **Drivers:** 2 x 5" Magnesium + Fountek Neo CD3.0 Ribbon.

### 2.2 The "Atmosphere & Speed" (Surrounds & Sub)
* **Surrounds:** Monitor Audio Silver SFX (Tri-pole).
    * **Logic:** Side-wall mounted in **DI-POLE** mode to widen the 2.67m room.
* **Subwoofer:** BK Electronics XXLS400-FF (Front Firing).
    * **Driver:** 12" Peerless XXLS (Long Throw / High Linear).
    * **Enclosure:** 50 Litre **Sealed** (Acoustic Suspension).
    * **Amp:** 400W RMS Discrete Bipolar.
    * **Role:** Fast, "dry" LFE for cinema; timbre-matched to the speed of the ribbons.

### 2.3 The "Brains & Muscle" (2026 Core)
* **Processor:** Marantz AV 30 (Reference Pre-amp / Dirac Live ART).
* **Power Amp:** Nord Three Purifi 1ET6525SA 5-Channel MKII.
    * **Custom Buffer Configuration (Nord Rev D):**
        * **Channels 1-3 (L/C/R):** Sparkos SS2590 Discrete Op-Amps (Class A warmth for Ribbons).
        * **Channels 4-5 (Rears):** OPA1612 (Ultra-clean, high-efficiency for surrounds).
* **DAC:** Denafrips Pontus 15th (R-2R Ladder DAC).

### 2.4 Visuals
* **Projector:** Epson EH-TW5910 (3LCD / 1080p).
* **Connectivity:** 48Gbps Fiber HDMI.

---

## 3. Room Acoustic Calibration (Dirac Live ART)
* **The Problem:** 35Hz Length Mode + 60Hz stacked Height/Width Modes.
* **The Solution:** **Active Room Treatment (ART)** logic.
    * **BK XXLS400 Setting:** High-pass set to 'Out/LFE' to allow Marantz full control.
    * **Logic:** Dirac ART will use the 5-channel Purifi array to "support" the sub, actively canceling room reflections at 35Hz and 60Hz.

---

## 4. Automation & Power Logic (12V Trigger Map)
| Trigger | Destination | Music (2.0) | Cinema (5.1) |
| :--- | :--- | :--- | :--- |
| **Out 1** | Nord 5-Ch Amp | **ON** | **ON** |
| **Out 2** | Projector Relay | **OFF** | **ON** |
| **Out 3** | BK XXLS400 Sub | **OFF** | **ON** |

---

## 5. Resale & Reinvestment Tracker
| Item for Sale | Est. Value (UK 2026) | Upgrade Target |
| :--- | :--- | :--- |
| **2x NCore NC400 Monos** | £900 | Nord Purifi 5-Ch |
| **IPL SW6 Sub (15")** | £350 | BK XXLS400-FF |
| **Total Recovery** | **£1250** | |
