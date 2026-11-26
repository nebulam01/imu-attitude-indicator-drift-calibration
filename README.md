# IMU Attitude Indicator — Drift, Noise & Calibration Lab

An interactive **Google Colab** engineering tool built with `ipywidgets`, `NumPy`, `Pandas`, and `Matplotlib` to simulate an **IMU attitude indicator** and test **gyro drift**, **sensor noise**, and **calibration / filtering** effects on roll and pitch tracking.

## Overview

Attitude indicators track orientation (`Roll` and `Pitch`), yet real IMUs suffer from bias drift, high-frequency noise, and calibration offsets[cite: 7]. This notebook lets you test different calibration modes, adjust roll/pitch angles, gyro drift rate, and IMU noise, inspect a 2D artificial horizon indicator alongside a roll tracking curve, and read a cause-and-effect verdict explaining why the result occurred.

### Included Calibration Modes
- **Uncalibrated (Raw Gyro):** Integrates raw gyro rates without bias compensation, illustrating time-accumulated drift.
- **Bias Calibrated (Gyro Only):** Compensates estimated gyro bias before integration while retaining remaining sensor noise and small residual drift.
- **Calibrated + Complementary Filter:** Combines bias-calibrated gyro integration with accelerometer tilt feedback to curb drift and balance noise.

## Key Features

- **Interactive English UI (`ipywidgets`):** Choose a calibration mode and adjust `Peak Roll [deg]`, `Peak Pitch [deg]`, `Gyro Drift [°/s]`, and `IMU Noise` sliders, updating live or via **Run IMU Test**.
- **2D Attitude Indicator & Roll Tracking Plot:** Displays a circular 2D artificial horizon (`True Horizon` vs. `Estimated Horizon`) next to the `Roll Tracking vs. Time` graph.
- **Error Metrics & Cause-and-Effect Verdict:** Reports `Roll RMSE`, `Final Roll Error`, and `Gyro Drift`, accompanied by a clear explanation of why the response behaves that way.

## How to Run in Google Colab

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Paste the IMU attitude indicator code into a code cell and run it.
3. Switch calibration modes and adjust drift or noise sliders to observe how calibration improves attitude stability.

## Engineering Notes

- Physical IMU attitude estimation also involves 3D rotation kinematics (quaternions/Euler rates), magnetometer/heading references, and vibration isolation; use this interactive lab to build intuition around drift, noise, and calibration trade-offs.
