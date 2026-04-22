Overview

Before interacting with the TurtleBot 4, your shell environment must be configured with specific ROS 2 Middleware (RMW) settings. This ensures your workstation can communicate with the robot via the Discovery Server protocol.

🎒 What you need

Prerequisites

Your ~/.bashrc file must be configured with the following environment variables:

    ROS_DOMAIN_ID: Unique ID for your robot network. We use: export ROS_DOMAIN_ID=1

    RMW_IMPLEMENTATION: Typically set to rmw_fastrtps_cpp. We use: export RMW_IMPLEMENTATION=rmw_fastrtps_cpp

    ROS_DISCOVERY_SERVER: The IP and port of the TurtleBot 4 discovery hub. We use: export ROS_DISCOVERY_SERVER=192.168.3.148:11811

    Super Client Configuration: XML path to allow your PC to "see" all nodes. We use: export ROS_SUPER_CLIENT=True

🚀 Let's Start!
Step 1: Wake Up the Secrets ⚡

We need to tell the computer to read its Prerequisites. Type this command into your terminal:

    source ~/.bashrc

(It won't look like much happened, but your computer just finished reading!)
Step 2: Look for the Robot! 🕵️‍♂️

Now, let's see if the robot is sending any data. Type this to see a list of everything the robot is sending:

    ros2 topic list

🎉 Did it work?

Check your screen! * If you see a BIG list of words (like /battery or /scan or /cmd or /cmd_vel), then HOORAY! You did it! Your computer can see all the details of the robot is publishing. 🥳

    If the list is empty, the robot might be sleeping. Make sure it's turned on and try again!