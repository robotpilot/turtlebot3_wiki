.. _chapter_teleoperation:

Teleoperation
=============

.. image:: _static/software/remote_pc_and_turtlebot.png
    :align: center

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame``.

.. WARNING:: Make sure to run the :ref:`[Bringup]<chapter_bringup>` instruction before teleoperation.

.. WARNING:: Be careful when testing the robot on the table as the robot might fall.

.. TIP:: The teleoperation is supposed to be running on the remote PC. **Follow the instruction on your Remote PC**.

TurtleBot3 can be teleoperated by various devices. It is tested with several wireless devices such as PS3, XBOX 360, ROBOTIS RC100 and etc. Examples shown here(except the LEAP Motion) can be launched by ROS on Ubuntu mate 16.04 with Raspberry Pi 3 and OpenCR which controls DYNAMIXEL.

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/Z4s18hlazb4" frameborder="0" allowfullscreen></iframe>

|

Keyboard
--------

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

[``Remote PC``] Launch the file for simple teleoperation test.

.. code-block:: bash

  roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

[``Remote PC``] If the program is successfully launched, the following instruction will be appeared to the terminal window.

.. code-block:: bash

  Control Your Turtlebot3!
  ---------------------------
  Moving around:
          w
     a    s    d
          x

  w/x : increase/decrease linear velocity
  a/d : increase/decrease angular velocity
  space key, s : force stop

  CTRL-C to quit

RC100
-----

The settings for ROBOTIS RC100 controller is included in the OpenCR firmware.

PS3 Joystick
------------

[``Remote PC``] Connect PS3 Joystick to the remote PC via Bluetooth or with USB cable.

[``Remote PC``] Install packages for teleoperation using PS3 joystick.

.. code-block:: bash

  sudo apt-get install ros-kinetic-joy ros-kinetic-joystick-drivers ros-kinetic-teleop-twist-joy

[``Remote PC``] Launch teleoperation packages for PS3 joystick.

.. code-block:: bash

  roslaunch teleop_twist_joy teleop.launch

XBOX 360 Joystick
-----------------

[``Remote PC``] Connect XBOX 360 Joystick to the remote PC with Wireless Adapter or USB cable.

[``Remote PC``] Install packages for teleoperation using XBOX 360 joystick.

.. code-block:: bash

  sudo apt-get install xboxdrv ros-kinetic-joy ros-kinetic-joystick-drivers ros-kinetic-teleop-twist-joy


[``Remote PC``] Launch teleoperation packages for XBOX 360 joystick.

.. code-block:: bash

  xboxdrv --silent
  roslaunch teleop_twist_joy teleop.launch

Wii Remote
----------

[``Remote PC``] Connect Wii remote to the remote PC via Bluetooth.

[``Remote PC``] Install packages for teleoperation using Wii remote.

.. code-block:: bash

  rosdep install wiimote
  rosmake wiimote

[``Remote PC``] Run teleoperation packages for Wii remote.

.. code-block:: bash

  rosrun wiimote wiimote_node.py
  rosrun learning_wiimote turtle_teleop_wiimote

Nunchuk
-------

(TODO)

Android App
-----------

Download `ROS Teleop`_ and run the application.


LEAP Motion
-----------

[``Remote PC``] Connect LEAP motion to the remote PC via Bluetooth.

[``Remote PC``] Install packages for teleoperation using LEAP motion.

- https://www.leapmotion.com/setup
- https://developer.leapmotion.com/downloads/sdk-preview

.. code-block:: bash

  leapd
  LeapCommandPanel
  git clone git@github.com:warp1337/rosleapmotion.git

[``Remote PC``] Run teleoperation package for LEAP motion.

.. code-block:: bash

  rosrun leap_motion sender.py

Myo
---

(TODO)

.. _ROS Teleop: https://play.google.com/store/apps/details?id=com.github.rosjava.android_apps.teleop.indigo
