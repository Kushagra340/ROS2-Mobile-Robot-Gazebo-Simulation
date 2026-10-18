# 🤖 ROS 2 & Gazebo Classic Simulation Guide

## 1. Differential Drive Plugin Physics (`kushagrabot_gazebo.xacro`)
The robot simulation uses the `gazebo_ros_diff_drive` plugin to model realistic ground interaction:
- **Wheel Separation**: $0.095\text{ m}$ (matches physical baseline).
- **Wheel Diameter**: $0.034\text{ m}$ ($34\text{mm}$ silicone rubber wheels).
- **Torque Limit**: $0.5\text{ N}\cdot\text{m}$ (matches N20 30:1 geared torque output).
- **Friction Parameters**:
  - Drive Wheels: $\mu_1 = 1.0, \mu_2 = 1.0$ (High-traction silicone).
  - Caster Wheel: $\mu_1 = 0.001, \mu_2 = 0.001$ (Frictionless omnidirectional support).

## 2. SLAM Toolbox Integration
Online synchronous 2D mapping uses `slam_toolbox` subscribing to simulated laser scans:
- **Map Resolution**: $0.05\text{ m/pixel}$
- **Scan Range**: $0.1\text{ m}$ min, $4.0\text{ m}$ max
- **Target Coordinate Frames**:
  $$\text{map} \longrightarrow \text{odom} \longrightarrow \text{base\_footprint} \longrightarrow \text{base\_link}$$
