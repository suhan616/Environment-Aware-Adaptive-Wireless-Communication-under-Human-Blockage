# Environment-Aware-Adaptive-Wireless-Communication-under-Human-Blockage
MINI PROJECT on Environment-Aware Adaptive Wireless Communication under Human Blockage
Environment-Aware Adaptive Wireless Communication under Human Blockage




📌 Project Overview

This project aims to develop an environment-aware adaptive wireless communication system. Traditional IoT and wireless setups often suffer from dropped packets or wasted energy due to unexpected environmental changes. Specifically, our research focuses on analyzing and mitigating the effects of human blockage on signal integrity.

By utilizing ESP32 microcontrollers, we monitor the Received Signal Strength Indicator (RSSI) to detect human-induced signal attenuation and dynamically adjust the Transmit (Tx) power to maintain a stable communication link.

⚠️ Problem Statement

Wireless signals (especially at higher frequencies like 2.4 GHz used in modern Wi-Fi/IoT) are highly susceptible to attenuation by the human body, which is primarily composed of water.

Static environments yield predictable path loss.

Dynamic environments (with moving humans) cause severe, sudden RSSI fluctuations.

Without environmental adaptivity, systems experience severe packet loss when Line-of-Sight (LoS) is broken, or they waste energy by constantly transmitting at maximum power.

🎯 Core Objectives

Analyze Human Blockage: Understand how a human crossing the Line-of-Sight affects RSSI and overall signal power.

Establish Baselines: Map out the static path loss (RSSI vs. Distance) in a clear environment.

Adaptive Feedback Loop: Implement dynamic adjustments (Transmit power scaling) to react to sharp RSSI dips and maintain stable communication.

🛠️ Hardware & Software Setup

Microcontrollers: 2x ESP32 Development Boards (NodeMCU/WROOM)

Communication Protocol: Half-Duplex channel (ESP-NOW / UDP)

Development Environment: Arduino IDE / ESP-IDF

Data Analysis: Python / MATLAB / Excel (for curve fitting and visualization)

📊 Current Progress & Results

Hardware Profiling & Baseline Setup
We have successfully established a half-duplex communication channel between a Transmitter (Tx) and a Receiver (Rx) ESP32 node. We studied the onboard PCB antenna's directivity and characterized the programmable Tx power levels (ranging from 2dBm to 20dBm).

RSSI vs. Distance Analysis
We logged raw RSSI values at specific distance intervals in a clear LoS environment to establish our baseline path loss model.

The graph above demonstrates the average RSSI drop as distance increases. Notice the distinct drop-off around the 10-unit mark before stabilizing.

Signal Strength Curve Fitting
To accurately model the environment, we plotted Signal Strength (Power) against Distance and applied a logarithmic curve fit.

This empirical data aligns closely with standard theoretical path-loss models (where power drops logarithmically with distance). This accurate baseline allows us to identify sudden deviations as "Blockage Events".

🚀 Expected Outcomes & Future Work

[ ] Upgrade to Full-Duplex: Transition to a two-way, full-duplex communication system to allow for real-time Tx control feedback.

[ ] Dynamic Power Control Algorithm: Deploy a closed-loop system that detects abnormal RSSI drops (human shadowing) and immediately commands the Tx node to increase transmitting power.

[ ] Performance Metrics: Rigorously measure the reduction in packet loss and latency once the adaptive power system is active compared to a static-power baseline.
