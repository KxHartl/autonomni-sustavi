# Autonomous systems: ROS 2 homework

**Autonomni sustavi**

> Autonomous Systems, BSc in Mechatronics and Robotics, FSB, University of Zagreb, 2024

![ROS 2](https://img.shields.io/badge/ROS%202-22314E?logo=ros&logoColor=white)
![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![Gazebo](https://img.shields.io/badge/sim-Gazebo-F58113)
![RViz](https://img.shields.io/badge/viz-RViz2-22314E)

Homework for the bachelor course Autonomous Systems, written as ROS 2 Python nodes. The assignments go
from a simple publisher and subscriber, through tf2 with turtlesim and a robot arm model in RViz,
to a TurtleBot3 that finds its way around obstacles with the Bug2 algorithm in Gazebo.

## What's inside

| Folder | What it does |
|---|---|
| `zadaca_04` | Two nodes: `brojcanik` publishes a counter on `broj` once a second, and `kvadriranje_broja` squares it and publishes the result on `kvadrat_broja`. |
| `zadaca_05` | turtlesim with tf2: a broadcaster publishes the turtle's frame, and a goal node takes a goal set in RViz and drives the turtle towards it. |
| `zadaca_06` | A KUKA LBR iiwa 14 model (URDF and meshes) moved by a joint state publisher and shown in RViz. |
| `zadaca_07` | Bug2 navigation for a TurtleBot3 in Gazebo, with an arena and two maze worlds, a node that turns the laser scan into two front range sensors, and a tracker that shows the robot's path and the goal in RViz. |

## How to run

`zadaca_06` and `zadaca_07` are complete ROS 2 packages under `src/`. Build and launch them from
their folder:

```bash
cd zadaca_07
colcon build
source install/setup.bash
ros2 launch zadaca_07 bug.launch.py
```

`bug.launch.py` starts Gazebo with `Arena_1.world`, spawns the TurtleBot3 and starts the Bug2
node and RViz. It needs `gazebo_ros` and `turtlebot3_gazebo`. For the robot arm:

```bash
cd zadaca_06
colcon build
source install/setup.bash
ros2 launch zadaca_06 zadaca_06.launch.py
```

## License

[Apache-2.0](LICENSE). It covers the author's own work in this repository. Third-party parts keep their own licences.
