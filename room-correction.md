https://housecurve.com/

# Calibration & Tuning Workflow (2026)

## 1. Physical Diagnostics (The "REW Baseline")
Before engaging digital correction, we use REW to identify the physical limits of the rental room.

* **Mic Setup:** UMIK-1 on a tripod at the Main Listening Position (MLP).
* **Orientation:** **90-degree** (pointing at the ceiling) using the specific 90° calibration file. This is mandatory for multi-speaker integration.
* **Objective:** Run a full-range sweep (10Hz - 20kHz) on the Left/Right towers alone.
    * **Look for:** The 35Hz Length Mode peak. If it exceeds +12dB, move the towers 5cm-10cm further from the front wall.
    * **Bookshelf Check:** Run a sweep, then add/remove books from your rear shelf. Look for a reduction in "ringing" on the **Waterfall Graph** (aim for T30 < 400ms).

## 2. Dirac Live ART (Active Room Treatment)
This is the "Brain" of your system. Unlike standard EQ, ART uses your center and surrounds to "suck" bass energy out of the room.

* **Measurement Density:** For ART to work in a narrow room, you need **9-13 measurement points**.
    * *Tip:* Create a "tight" 60cm cube around your head for the first 5 measurements, then expand slightly.
* **Support Settings (The Secret Sauce):** - **Towers & Sub:** Set as "Primary" actuators.
    - **Center & Surrounds:** Set as "Support" actuators.
    - **Range:** Set the ART support range to **30Hz - 150Hz**. This allows the Monitor Audio surrounds to help "eat" the 60Hz room mode without overtaxing their small drivers.

## 3. Post-Calibration Validation (The "Verification Loop")
Once the Dirac filter is loaded into the Marantz AV 30, we return to REW to verify the "Speed" of the system.

* **Impulse Response:** Check that the Fountek Ribbons and the BK Subwoofer are "Time Aligned." The initial spike should be a single, clean line.
* **Group Delay:** Ensure the bass from the 15" sub (if still in use) or the 12" BK doesn't "lag" behind the towers by more than 20ms at 40Hz.
* **Waterfall Graph:** This is the ultimate test. With ART 'ON', the 35Hz room boom should disappear almost instantly.

## 4. Advanced: Custom Target Curves
If the system sounds too "dry" (a common side-effect of perfect correction):
* **REW Filter Export:** Generate a "House Curve" in REW (usually a +4dB slope from 100Hz down to 20Hz).
* **Dirac Import:** Import this `.targetcurve` file into Dirac Live to restore that "tactile fun" for movies without re-introducing the "boom."


