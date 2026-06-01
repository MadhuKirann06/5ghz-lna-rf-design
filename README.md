# 5ghz-lna-rf-design
Design and simulation of a 5 GHz Low Noise Amplifier (LNA) for 5G wireless systems using QucsStudio, evaluating S-parameters, gain, and stability.
# Design and Simulation of a 5 GHz Low Noise Amplifier (LNA) for 5G Wireless Systems ⚡

## Circuit Schematic & Simulation Workspace
![QucsStudio LNA Schematic](https://drive.google.com/file/d/1hSKhssVlYqJb4Thoiv0F6N8Je5ZpWSEl/view?usp=sharing)

## S-Parameter & Smith Chart Performance Results
![LNA Simulation Results](https://drive.google.com/file/d/1RmJ3sQIauNceA-lgGqO1IxmBt9QqJu5U/view?usp=sharing)

## Project Description
This repository features the high-frequency design, modeling, and S-parameter simulation of a $5\text{ GHz}$ Low Noise Amplifier (LNA) optimized for next-generation 5G wireless receiver front-ends. LNAs are critical components in RF receivers, tasked with amplifying weak signals captured by the antenna while introducing minimal noise. This project leverages an active transistor architecture model (`atf34143.s2p`) to evaluate network matching configurations, stability conditions ($K$-factor), input/output return losses, and power gain across a $1\text{ GHz}$ to $10\text{ GHz}$ test spectrum.

## Circuit Architecture & S-Parameter Telemetry

### 1. Circuit Design & Test Bench Setup
* **Active Device:** Modeled around the `atf34143` transistor configuration utilizing touchstone S-parameter file parameters (`.s2p`).
* **RF Isolation Network:** Configured with an inductive RF choke element ($L_1 = 3\text{ nH}$) and isolation resistance ($R_1 = 22\ \Omega$) to manage stabilization constraints.
* **Port Characteristics:** Terminated with standard $50\ \Omega$ source ($P_1$) and load ($P_2$) reference impedances.

### 2. Math & Simulation Performance Telemetry (At 5 GHz Operating Window)
The circuit performance metrics were evaluated via the following scattering parameter expressions:

* **Power Gain ($S_{21}$):** Reached a stable simulation gain peak of **$2.37\text{ dB}$** directly within the target $5\text{ GHz}$ frequency marker window.
* **Input Return Loss ($S_{11}$):** Achieved an input port reflection coefficient of **$-1.21\text{ dB}$** at $5\text{ GHz}$, representing the impedance matching profile of the front-end network.
* **System Stability ($K$-Factor Calculation):** Configured automated solver equations to track the Stern stability criteria:

$$D = S_{11}S_{22} - S_{12}S_{21}$$

$$K = \frac{1 - |S_{11}|^2 - |S_{22}|^2 + |D|^2}{2|S_{12}S_{21}|}$$

The solver validated that the circuit satisfies baseline stability factors ($K = 1$ at $1\text{ GHz}$) before scaling across high-frequency ranges.
* **Impedance Mapping:** Tracked complex input/output reflections using multi-trace Smith Chart trajectories to visualize the source/load tuning limits.

## CAD & Simulation Tools Used
* **Simulation Workspace:** QucsStudio (Quite Universal Circuit Simulator Tools)
* **Analysis Domain:** Linear S-Parameter Sweep Framework ($1\text{ GHz}$ to $10\text{ GHz}$, 201 data collection sweep points)
