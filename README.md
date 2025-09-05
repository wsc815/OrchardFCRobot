# OrchardFCRobot
>Orchard Follow & Carry Robot

---
## Enviroment Dependency
Ubuntu:20.04
ROS Noetic
gazebo models
```commandline
git clone https://github.com/osrf/gazebo_models.git
```
ROS dependency
```commandline
sudo apt-get install ros-noetic-velocity-controllers
sudo apt-get install ros-noetic-gazebo-ros-control
sudo apt install ros-noetic-ros-controllers
sudo apt install ros-noetic-teleop-twist-keyboard
sudo apt-get install ros-noetic-hector-gazebo-plugins
```

---
## Gazebo Simulation
Setup
```commandline
cd OrchardFCRobot
catkin_make
source devel/setup.bash
```

Add enviroment paraments
```commandline
sudo gedit ~/.bashrc
```

```commandline
# Gazebo custom models and worlds
# --- Gazebo official env ---
if [ -f /usr/share/gazebo/setup.sh ]; then
  source /usr/share/gazebo/setup.sh
fi

# --- Custom models / worlds ---
export GAZEBO_MODEL_PATH="/usr/share/gazebo-11/models:${HOME}/OrchardFCRobot/src/gazebo_models"
export GAZEBO_MODEL_PATH="/usr/share/gazebo-11/models:${HOME}/OrchardFCRobot/src/gazebo_models_worlds_collection/models"
export GAZEBO_RESOURCE_PATH="/usr/share/gazebo-11:${HOME}/OrchardFCRobot/src/gazebo_models_worlds_collection/worlds"
export GAZEBO_MODEL_PATH="/usr/share/gazebo-11/models:${HOME}/OrchardFCRobot/src/agilex_scout_sim/scout_gazebo_sim/models"
# 禁止 Gazebo 每次联网更新模型
export GAZEBO_MODEL_DATABASE_URI=""
```

Run Simulation
```commandline
roslaunch scout_gazebo scout_gazebo.launch 
```

Keyboard control
```commandline
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

---
## Orchard Experiment


---
## Reference
https://github.com/osrf/gazebo_models.git
https://github.com/agilexrobotics/scout_ros