# 🤖 ROS 2 Autonomous Mobile Robot Digital Twin & Simulation (Gazebo Classic)

[![ROS 2](https://img.shields.io/badge/ROS_2-Humble-3498DB?style=for-the-badge&logo=ros&logoColor=white)](https://docs.ros.org/en/humble/)
[![Gazebo](https://img.shields.io/badge/Gazebo-Classic_11-orange?style=for-the-badge)](https://gazebosim.org/)
[![SLAM](https://img.shields.io/badge/SLAM-SLAM_Toolbox-green?style=for-the-badge)]()
[![RViz2](https://img.shields.io/badge/Visualization-RViz2-red?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

> **A physics-accurate Gazebo Classic digital twin and ROS 2 simulation environment for differential-drive mobile robots.**  
> Features parameterized **URDF/Xacro kinematics**, realistic surface friction models, simulated differential drive odometry, **SLAM Toolbox** 2D occupancy grid mapping, and autonomous trajectory control scripts.

---

## 🚀 Quick Launch Playbook

### 1. Build the ROS 2 Workspace
```bash
source /opt/ros/humble/setup.bash
colcon build --symlink-install
source install/setup.bash
```

### 2. Launch Gazebo Simulation World
```bash
ros2 launch kushagrabot_description gazebo.launch.py
```

### 3. Launch Online 2D SLAM (SLAM Toolbox)
```bash
ros2 launch kushagrabot_description slam.launch.py
```

### 4. Teleoperate or Run Autonomous Trajectory
```bash
# Autonomous Square Trajectory Engine
ros2 run kushagrabot_description shape_controller.py
```

---

## 📂 Repository Directory Structure

```text
ROS2-Mobile-Robot-Gazebo-Simulation/
├── README.md                           # Master simulation guide & launch commands
├── kushagrabot_description/
│   ├── CMakeLists.txt
│   ├── package.xml
│   ├── urdf/                           # kushagrabot.urdf.xacro, kushagrabot_gazebo.xacro
│   ├── launch/                         # display, gazebo, hardware, slam launch files
│   ├── rviz/                           # Pre-configured RViz visualization profiles
│   ├── config/                         # controllers.yaml, ekf.yaml
│   ├── worlds/                         # Simulation maze and obstacle environments
│   └── scripts/                        # shape_controller.py, calibrate_encoders.py
└── docs/
    └── simulation_and_slam_guide.md    # Differential drive physics & SLAM parameters
```

---
## 📜 License
Open-source under the [MIT License](LICENSE).
