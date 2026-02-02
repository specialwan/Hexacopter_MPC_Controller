# MPC Package

ROS package for Model Predictive Control (MPC) trajectory following with LOS guidance.

## Description

This package contains MPC-based trajectory follower implementation for marine vessels or similar systems with:
- Trajectory publisher with LOS guidance
- MPC trajectory follower
- Data logger for LOS guidance

## Package Contents

- `scripts/` - Python scripts for MPC controller, trajectory publisher, and data logger
- `launch/` - Launch files for running the system
- `src/` - Source code files

## Usage

To run the trajectory following with LOS guidance and logger:

```bash
roslaunch mpc_pkg traj_los_guidance_with_logger.launch
```

## Requirements

- ROS (Robot Operating System)
- Python dependencies (add specific requirements if needed)

## License

(Add your license here)
