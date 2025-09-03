# ROS 2 Humble Robotic Arm Simulation

This repository contains the URDF/Xacro model of the Arduinobot robotic arm and the required launch files for visualization in **RViz2** using ROS 2 Humble.

---

##  Prerequisites

- Ubuntu 22.04
- [ROS 2 Humble](https://docs.ros.org/en/humble/Installation.html)
- `colcon` build system
- `xacro` package

Install required tools:
```bash
 
sudo apt update
sudo apt install ros-humble-desktop ros-humble-xacro

1. Create a ROS 2 Workspace
# Create and navigate to workspace

mkdir -p ~/arduinobot_ws/src
cd ~/arduinobot_ws/src

 2. Clone the Repository
git clone https://github.com/<your-username>/arduinobot.git arduinobot_description

 3. Build the Workspace
cd ~/arduinobot_ws
colcon build

 4. Source the Setup File

Every new terminal session:

source install/setup.bash

 5. Verify URDF with Xacro

Convert .xacro to .urdf:

ros2 run xacro xacro ~/arduinobot_ws/src/arduinobot_description/urdf/arduinobot.urdf.xacro -o ~/arduinobot_ws/src/arduinobot_description/urdf/arduinobot.urdf

 6. Launch in RViz2
ros2 launch urdf_tutorial display.launch.py model:=/home/$USER/arduinobot_ws/src/arduinobot_description/urdf/arduinobot.urdf.xacro

 7. Use Joint State Publisher GUI

This allows you to move joints interactively:

ros2 run joint_state_publisher_gui joint_state_publisher_gui

 Folder Structure
arduinobot_ws/
  ├── src/
  │    ├── arduinobot_description/
  │    │     ├── urdf/
  │    │     │     ├── arduinobot.urdf.xacro
  │    │     ├── meshes/
  │    │     │     ├── *.STL

 Troubleshooting

Model not showing in RViz:

Check that model:= points to the correct .urdf.xacro path.
xml.parsers error:
Run pip3 uninstall xml if a wrong Python package is installed.

```
#CAD FILES :
All the files are in STL format . All the parts were designed using Fusion 360 and these are ready to go for 3D Printing .
This is for educational purposes not for any financial gain

For any mistakes found or any queries :
Email: rahulsankey285@gmail.com
