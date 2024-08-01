# naoqi_rviz

This repo intends to simplify the installation and usage of naoqi system with rviz2. This repository contains only the mesh packages of nao and pepper. For core usage, use [AIResearchLab/naoqi](https://github.com/AIResearchLab/naoqi). For visualization only tasks, follow the below instructions.

## ROS based installation

Create the workspace
```bash
mkdir -p workspace/src
cd workspace/src
```

### RVIZ Installation

Clone the repository with submodules

```bash
git clone --recursive https://github.com/AIResearchLab/naoqi_rviz.git
```

### Build workspace 

According to [ros-naoqi/naoqi_driver2](https://github.com/ros-naoqi/naoqi_driver2.git) developers comments, [AIResearchLab/naoqi](https://github.com/AIResearchLab/naoqi) works with both AMD64 and ARM64 computers while [AIResearchLab/naoqi_rviz](https://github.com/AIResearchLab/naoqi_rviz.git) can only be build on AMD64 computers.

```bash
cd workspace
rosdep install --from-paths src --ignore-src --rosdistro $ROS_DISTRO -y
```

```bash
colcon build
```

to agree to and skip [license](https://github.com/ros-naoqi/naoqi_driver2#license-of-the-meshes) prompt, run,

```bash
I_AGREE_TO_NAO_MESHES_LICENSE=1 I_AGREE_TO_PEPPER_MESHES_LICENSE=1 colcon build
```