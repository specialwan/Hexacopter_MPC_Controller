# Hexacopter Trajectory Tracking using MPC and LOS Guidance

This repository contains the implementation of a **real-time trajectory tracking framework for a hexacopter UAV** using **Model Predictive Control (MPC)** combined with **Line-of-Sight (LOS) guidance**.  
The project was developed as part of an undergraduate thesis and focuses on bridging advanced control theory with practical real-world implementation on a PX4-based UAV platform.


## Overview

The proposed control architecture follows a **hierarchical control structure**:
- **LOS guidance** is used to generate smooth and continuous reference trajectories.
- **MPC** is implemented as an **outer-loop controller** to regulate the translational motion of the UAV.
- **Attitude and angular rate stabilization** are handled by the built-in **PID controllers of the PX4 autopilot**.

The MPC controller runs **offboard** on a companion computer and communicates with PX4 via **MAVROS**.  
The system is validated through both **Software-In-The-Loop (SITL)** simulation and **real-time flight experiments** on a physical hexacopter.

## System Architecture

- Path reference → LOS guidance  
- LOS output (position, velocity, yaw reference) → MPC outer loop  
- MPC output (translational acceleration) → attitude and thrust setpoints  
- PX4 inner loop (PID) → motor commands  

This structure allows the use of advanced predictive control while maintaining compatibility with a commercial autopilot.

## Tools and Technologies

- **PX4 Autopilot**
- **ROS (Robot Operating System)**
- **MAVROS**
- **Gazebo (SITL simulation)**
- **Raspberry Pi** (companion computer)
- **Model Predictive Control (MPC)**
- **Line-of-Sight (LOS) guidance**

## Key Features

- Real-time MPC-based outer-loop control for hexacopter UAV
- LOS guidance for smooth 3D trajectory tracking
- Helical trajectory tracking in three-dimensional space
- Simulation-to-hardware workflow (SITL → real flight)
- Comparative evaluation against PX4 PID position control

## Experimental Results

Real-time flight experiments demonstrate that the proposed MPC–LOS framework:
- Achieves stable and smooth tracking of a 3D helical trajectory
- Reduces trajectory tracking RMSE by **9.46%**
- Improves mission completion time by **18.2%**
compared to the conventional PX4 PID-based position controller.

## Notes

- This repository focuses on **trajectory tracking**, not low-level motor control.
- MPC parameters are tuned for real-time feasibility on embedded hardware.
- The code is provided for research and educational purposes.