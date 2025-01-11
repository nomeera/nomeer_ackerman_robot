# nomeer_ackerman_robot

## Overview
The **Ackerman Robot** is a ROS 2-based robot designed with an Ackerman steering mechanism. This project includes two main packages:

1. **robot_description** - Handles the robot’s physical description and integration with Gazebo and Rviz.
2. **teleop_twist_keyboard** - Enables manual control of the robot using keyboard inputs.

---

## Package Details

### 1. **robot_description**
This package contains all the necessary files to describe the Ackerman Robot and manage its simulation in Gazebo.

#### Directory Structure:
- **config/**: Contains configuration files for Gazebo bridge parameters.
- **launch/**: Includes launch files to start the Gazebo world and robot description.
  - Example command to launch:
    ```bash
    ros2 launch robot_description ackerman_robot.launch.py
    ```
- **models/**: Contains the Ackerman Robot’s SDF file.
- **worlds/**: Includes custom Gazebo world files, such as `warehouse.sdf`.
- **rviz/**: Includes the Rviz2 configuration file.
- **CMakeLists.txt** and **package.xml**: Define package dependencies and build instructions.

### 2. **teleop_twist_keyboard**
This package allows users to control the Ackerman Robot via keyboard input. It provides:
- A Python-based script to capture keyboard inputs and send velocity commands to the robot via `/cmd_vel`.

---

## Getting Started

### Prerequisites
Ensure you have the following installed:
- ROS 2 (Humble)
- Gazebo Harmonic

### Installation
1. Clone the repository to your workspace:
   ```bash
   git clone https://github.com/nomeera/nomeer_ackerman_robot.git
   ```
2. Build the workspace:
   ```bash
   cd <workspace>
   colcon build --symlink-install --allow-overriding teleop_twist_keyboard
   ```
3. Source the workspace:
   ```bash
   source install/setup.bash
   ```

---

## Usage

### Launching the Robot in Gazebo
Run the following command to launch the robot in the warehouse simulation:
```bash
ros2 launch robot_description ackerman_robot.launch.py
```

### Controlling the Robot
1. Open a new terminal and source the workspace.
2. Run the teleoperation script:
   ```bash
   ros2 run teleop_twist_keyboard teleop_twist_keyboard
   ```

Follow the on-screen instructions to control the robot with your keyboard.

---

## Robot Image
![](/docs/Screenshot%20from%202025-01-12%2001-30-09.png)
---

## Future Plans
- Implement autonomous navigation for the Ackerman Robot.
- Develop advanced motion planning algorithms tailored for the Ackerman steering mechanism.

---

## License
This project is licensed under the [Apache License](src/robot_description/LICENSE).

---

