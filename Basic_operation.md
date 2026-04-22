**Basic Operations of the turtlebot**

Overview

This task covers manual movement (Teleop), controlling the User LEDs, and playing audio sequences on the TurtleBot 4.

2.1 Manual Control (Teleop)

Drive the robot using your keyboard. This command ensures the messages are "stamped" for compatibility:


    ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -p stamped:=true

2.2 LED Control

The /hmi/led topic uses BEST_EFFORT reliability.

    LED IDs: 0 (User LED 1), 1 (User LED 2)

    Colors: 0: Off, 1: Green, 2: Red, 3: Yellow

Turn on Green LED (Blinking):


    ros2 topic pub --once /hmi/led turtlebot4_msgs/msg/UserLed "{led: 0, color: 1, blink_period: 500, duty_cycle: 0.5}"

Stop Blinking / Turn Off:


    ros2 topic pub -t 5 -r 5 /hmi/led turtlebot4_msgs/msg/UserLed "{led: 0, color: 0, blink_period: 0, duty_cycle: 0.0}"

2.3 Audio Sequences

Play a sequence of two notes (440Hz and 660Hz) using the Action server:


    ros2 action send_goal --feedback /audio_note_sequence irobot_create_msgs/action/AudioNoteSequence \
    '{iterations: 1, note_sequence: {notes: [{frequency: 440, max_runtime: {sec: 0, nanosec: 300000000}}, {frequency: 660, max_runtime: {sec: 0, nanosec: 300000000}}], append: false}}'