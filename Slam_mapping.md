SLAM Mapping & Camera Integration

Overview

Generate a 2D map of your environment using SLAM (Simultaneous Localization and Mapping) while enabling the OAK-D camera for a first-person view.

Execution Steps

1. Launch SLAM:
    
        ros2 launch turtlebot4_navigation slam.launch.py

2. Enable Camera (SSH to Robot):
    Open a new terminal, SSH into the robot and run the command:

        ssh ubuntu@<robot-ip-address>
        # Password: turtlebot4
    
        command:- ros2 launch turtlebot4_bringup oakd.launch.py

3. Visualize in Rviz:
    
        ros2 launch turtlebot4_viz view_navigation.launch.py

4. Drive and Map:
    
        ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -p stamped:=true

5. Saving the Map

    Once the map looks complete, run the following to save it to your local machine:

        ros2 run nav2_map_server map_saver_cli -f "my_map_name" 

    instead of my_map_name, give your map-name which you created.

6. To view the generated image:

        xdg-open my_map_name.pgm