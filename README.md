# Demo Robot Ros

ROS2 package containing files for both Demo Robot simulation and physical control, including Nav2.

## Project Structure

A high-level view of the projects structure:
- launch: Launch files
- description: URDF files 
- config: Configuration files
- maps: maps used for Nav2
- docs: Documentation and diagrams

## Dependencies

To be determined

## Building

Build the package in the desired workspace:
```
colcon build --symlink-install
```

## Running

### Simulation

Launch Gazebo simulation of Demo Robot:
```
ros2 launch demo_bot_ros launch_sim.launch.py use_ros2_control:=true
```

### Physcial Robot

Launch Demo Robot:
```
ros2 launch demo_bot launch_robot.launch.py
```

Run `teleop_twist` to control the Robot:
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

### Nav2

Run rviz2 to input Goal Poses
```
rviz2
```
Note: in order to view the map, add the map in Rviz using `/map` as the topic before launching the map server.

Launch the `map_server`:
```
ros2 launch retrieval_robot_ros map_server.launch.py
```

Run Nav2 bringup:
```
ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true
```

## To-Do

- Constrain Nav2 to Grid