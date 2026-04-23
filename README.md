Overview

Before interacting with the TurtleBot 4, your shell environment must be configured with specific ROS 2 Middleware (RMW) settings. This ensures your workstation can communicate with the robot via the Discovery Server protocol.


🚀 Let's Start!

Step 1: Open the Terminator.

Step 2: Look for the Robot! 🕵️‍♂️

Check if lidar is running on the turtlebot. If not then run this command: 

        ros2 service call /start_motor std_srvs/srv/Empty {}
        
Now, let's see if the robot is sending any data. Type this to see a list of everything the robot is sending:

    ros2 topic list

🎉 Did it work?

Check your screen! * If you see a BIG list of words (like /battery or /scan or /cmd or /cmd_vel), then HOORAY! You did it! Your computer can see all the details of the robot is publishing. 🥳

    If the list is empty, the robot might be sleeping. Make sure it's turned on and try again!
