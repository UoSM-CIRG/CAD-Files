# Drone Dev Kit

This repository contains CAD files for various drone development kits. 
Included in this collection is a FreeCAD and Blender project file that allows you to:

- Visualize the complete assembly of the drone.
- Explore the drone structure allowing the removal or addition of parts to the assembly.
- Customize the drone or any of its parts.

## Contents

### [catkin_ws](./catkin_ws)

- **catkin_ws:** The main workspace.
  - **display_model:** A ROS package for displaying the model on RVIZ.
    - **description:** The model description urdf/xacro.
      - m500_jetson_rplidar_urdf/
      - m500_jetson_zed_rplidar_urdf/
      - m500_jetson_zed_urdf/
      - m500_urdf/
    - **launch:** Contains multiple launch files for different scenarios.
      - display_m500_jetson_rplidar.launch
      - display_m500_jetson_zed_rplidar.launch
      - display_m500_jetson_zed.launch
      - display_m500.launch
    - **rviz:** RViz configuration files for displaying various models.
      - m500_config.rviz

**Prerequisites**

Any ROS1 distro is needed to build the catkin workspace. Recommendation [ROS Noetic](http://wiki.ros.org/noetic/Installation).

**Installation**

```bash
source /opt/ros/{ros_distro}/setup.bash
cd {repo_location}/catkin_ws
catkin_make
source devel/setup.bash
```
Run the python script to unzip all mesh files.
```bash
python {repo_location}/catkin_ws/src/display_model/unzip_meshes.py
```

Example launch
```bash
roslaunch display_model display_m500.launch
```

### [ModalAI VOXL-m500](./voxl-m500)

The ModalAI VOXL-m500 in this repository is crafted with components from various sources. Following is a breakdown of its key parts:

- VOXL-Flight Deck Model: The flight deck model is sourced from [ModalAI's asset repository](https://developer.modalai.com/asset/6).
- Drone Frame: The frame of the drone is based on the HolyBro S500 model, available at [HolyBro's Wikifactory](https://wikifactory.com/+holybro/reference-frame-1/files) page.
- Landing Skid: The landing skid is adapted from the Sentinel Drone Step File, accessible through [ModalAI's Sentinel Functional Description](https://docs.modalai.com/sentinel-functional-description/#3d-step).
- Propellers: The propellers for the VOXL-m500 have a diameter of 10 inches and a pitch of 45 inches. You can obtain the propeller model from [Grabcad](https://grabcad.com/library/propeller-10x45-1).


| Drone                                                                 | FreeCAD                                                                       | Blender                                                               | RVIZ
|-----------------------------------------------------------------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------|---------------------------
|<img src="./voxl-m500/m500.png" alt="VOXL M500 Preview" width="200"/> | <img src="./voxl-m500/m500_CAD.png" alt="VOXL M500 CAD Preview" width="200"/> | <img src="./voxl-m500/m500_BLENDER.png" alt="VOXL M500 Blender Preview" width="200"/> | <img src="./voxl-m500/m500_RVIZ.png" alt="VOXL M500 RVIZ Preview" width="200"/>

- File format includes **.step**, **.stl**, **.urdf + .dae** 

Also include customized variant.
- Jetson Orin Nano Model: Jetson Orin Nano dev board is taken from [Nvidia Download Centre](https://developer.nvidia.com/embedded/downloads).
- Slamtec RPLidarS1 Model: The LiDAR models is available at [Slamtec Download](https://www.slamtec.ai/downloads/) page.
- Stereolabs Zed camera: The camera can be found at [Stereolabs's Support Centre](https://support.stereolabs.com/hc/en-us/articles/360007494333-Can-I-get-3D-models-and-dimensions-of-my-camera).

USD files for Omniverse and Isaac-Sim is also available. It is created using the [URDF importer](https://docs.omniverse.nvidia.com/isaacsim/latest/features/environment_setup/ext_omni_isaac_urdf.html). 

<img src="./voxl-m500_jetson-orin_zed-mini_rplidars1/m500_Omniverse.png" alt="VOXL M500 Omniverse Preview" width="500"/>