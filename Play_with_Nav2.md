Overview

Use a previously created map to navigate the TurtleBot 4 autonomously to a goal location.

Execution Steps

1. Launch Localization:
    
        ros2 launch turtlebot4_navigation localization.launch.py map:=my_map_name.yaml

2. Launch Nav2 Stack:

        ros2 launch turtlebot4_navigation nav2.launch.py

3. Visualize:

        ros2 launch turtlebot4_viz view_navigation.launch.py

4. Moving the Robot

    2D Pose Estimate for localization: In Rviz, click "2D Pose Estimate" and click/drag on the map at the robot's current physical location.

    Then you can see, on the left side in Rviz, localization and Navigation shows active now under Nav2 section.

    Nav2 Goal: You can find this in the toolbar on Rviz. Click "Nav2 Goal" and select a destination on the map. The robot will plan a path and move.

Once the robot reaches it destination, you can see the Feedback status as reached or success on the left side in Rviz under Nav2 section.

Incase you get Time Sync Error: sync the clocks of both your PC and the TurtleBot:

        sudo apt-get install ntpdate
        sudo ntpdate ntp.ubuntu.com

        then just type " date " on both PC and turtlebot. check the date and time.
