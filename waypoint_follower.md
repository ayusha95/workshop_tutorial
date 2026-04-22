Waypoint Route Planning

Instead of a single goal, use the Route tool to define a sequence of waypoints for the robot to follow in order.

Steps for Route Following

1. Launch Navigation:
                    
   First load the map and localize it:- 
                          
                          ros2 launch turtlebot4_navigation localization.launch.py map:=my_map_name.yaml

   Launch Nav2:- 
                         
                         ros2 launch turtlebot4_navigation nav2.launch.py

   Open Rviz to visualize:- 
                        
                        ros2 launch turtlebot4_viz view_navigation.launch.py

2. Localize: 
        
          Use the 2D Pose Estimate tool to ensure the robot’s position on the map matches reality.

3. Select Waypoint Mode: 

        In the Rviz "Panels" or tool header, ensure you are using the Nav2 Goal tool, but switch the mode to Waypoint/Route if using the specific Route Tool plugin.

4. Drop Waypoints: * Click on the map to set your first waypoint.

        Continue clicking to add subsequent waypoints (Point A -> Point B -> Point C).

5. Start Navigation: 

        Click the Start Waypoint Follower button in the Nav2 panel. The robot will now navigate to each point in the order they were placed.
