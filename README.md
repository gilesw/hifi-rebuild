# System Blueprint: The Transmission Line Purist (v5.0)

## 1. Executive Summary
A fully integrated 5.1 Home Theater and R-2R Music system. This build solves the "Clinical/Heat" issues of the legacy NCore/DIY era by moving to a consolidated Purifi amplification stage and a Reference-grade Marantz "Brain."

## 2. Hardware Manifest

### 2.1 Visuals (The "Big Screen")
* **Projector:** Epson EH-TW5910 (3LCD / Full HD 1080p).
* **Connectivity:** 48Gbps Active Optical HDMI (Fiber) to ensure handshake stability at 1080p over distance.
* **Automation:** Set to "Direct Power On" via Triggered AC Relay.

### 2.2 The "Front Three" (IPL Heritage)
* **Main Towers:** IPL S2TLM (8" Kevlar + Fountek CD3.0 Ribbon).
    * *Note:* Transmission Line design with 23Hz extension; used full-range for music.
* **Center:** IPL AVC-PRO (5" Magnesium + Fountek CD3.0 Ribbon).
    * *Note:* Timbre-matched to towers for seamless dialogue pans.

### 2.3 The "Surround Bubble" (Monitor Audio)
* **Rears:** Monitor Audio Silver SFX (Tri-pole / Angled Baffle).
    * **Setting:** Set to **DI-POLE** mode for the 2.67m narrow room to create a diffuse, immersive soundstage.
    * **Placement:** Side-wall mounted, 60cm above ear height.

### 2.4 The "Brains & Muscle" (2026 Core)
* **Processor:** Marantz AV 30 (Reference Pre-amp / Dirac Live ART).
* **Power Amp:** Nord Three Purifi 1ET6525SA 5-Channel MKII.
    * **Buffer:** Nord Rev D with Sparkos SS2590 (Front 3) & OPA1612 (Rears).
* **DAC:** Denafrips Pontus 15th (R-2R Ladder DAC).

---

## 3. Power & Automation Logic (12V Trigger Map)

The Marantz AV 30 acts as the "Master Controller."

| Trigger Out | Destination | Music Logic (CD) | Movie Logic (TV) |
| :--- | :--- | :--- | :--- |
| **Trigger 1** | Nord 5-Ch Amp | **ON** | **ON** |
| **Trigger 2** | Projector Relay | **OFF** | **ON** |
| **Trigger 3** | [Optional] Subwoofer | **OFF** | **ON** |

---

## 4. Signal Chain Optimization
1. **Music (Stereo):** Linux/CamillaDSP → Denafrips → Marantz (XLR In) → **Pure Direct Mode**.
   - *Result:* Nord Amp drives IPL Towers full-range. All other speakers/projector remain OFF.
2. **Movies (5.1):** Source → Marantz (HDMI In) → **Dirac Live ART**.
   - *Result:* Full 5.1 engagement. Dirac uses the Monitor Audio SFX and IPL Center to actively cancel room modes, tightening the bass from the TL towers.

## 5. Thermal & Efficiency Report
* **Idle State:** ~25W (Entire system).
* **Acoustic Note:** The "Curved Wall" section of the room helps break up high-frequency

## 6. Linux machine breakdown

### kodi

movie playing locked to the hdmi output

### music

https://lyrion.org/lms-server-repository/


