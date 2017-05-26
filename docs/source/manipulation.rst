.. _chapter_manipulation:

Manipulation
============

.. NOTE:: This instruction was tested on ``Ubuntu 16.04, Linux Mint 18.1`` and ``ROS Kinetic Kame``.

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/qbht0ssv8M0" frameborder="0" allowfullscreen></iframe>

|

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/Qhvk5cnX2hM" frameborder="0" allowfullscreen></iframe>

|

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

Install dependent packages for the Open-Manipulator.

.. code-block:: bash

  sudo apt-get install ros-kinetic-desktop-full ros-kinetic-moveit* ros-kinetic-dynamixel-sdk ros-kinetic-dynamixel-workbench-toolbox ros-kinetic-robotis-math ros-kinetic-industrial-core

.. code-block:: bash

  cd ~/catkin_ws/src/
  git clone https://github.com/ROBOTIS-GIT/open_manipulator.git
  cd ~/catkin_ws && catkin_make

If catkin_make command is completed without any errors, the preparation for Open-Manipulator is done.

Gazebo (3D)
-----------

Below command will load the Open-Manipulator on Gazebo environment.

.. code-block:: bash

  roslaunch open_manipulator_gazebo open_manipulator_gazebo.launch

.. image:: _static/manipulation/open_manipulator_gazebo_1.png

In order to control Open-Manipulator, please use topic publish with below command in a new terminal window.

.. code-block:: bash

  rostopic pub /open_manipulator_chain/joint2_position/command std_msgs/Float64 "data: 1.0" --once

.. image:: _static/manipulation/open_manipulator_gazebo_2.png

In order to run Open-Manipulator simulation with MoveIt!, open a new terminal window and enter below command.

.. code-block:: bash

  roslaunch open_manipulator_moveit open_manipulator_demo.launch use_gazebo:=true

.. image:: _static/manipulation/open_manipulator_moveit_sim_1.png

.. image:: _static/manipulation/open_manipulator_moveit_sim_2.png

In order to control gripper, please use topic publish with below command in a new terminal window.

.. code-block:: bash

  rostopic pub /robotis/open_manipulator/gripper std_msgs/String "data: 'grip_on'" --once

.. image:: _static/manipulation/open_manipulator_gripper.png

Platform
-----------

Below command will load the Open-Manipulator with DYNAMIXEL X-series.

.. code-block:: bash

  roslaunch open_manipulator_dynamixel_ctrl dynamixel_controller.launch

In order to run Open-Manipulator simulation with MoveIt!, open a new terminal window and enter below command.

.. code-block:: bash

  roslaunch open_manipulator_moveit open_manipulator_demo.launch

.. image:: _static/manipulation/open_manipulator_moveit_real_1.png

.. image:: _static/manipulation/open_manipulator_moveit_real_2.png

.. image:: _static/manipulation/open_manipulator_moveit_real_3.png

.. image:: _static/manipulation/open_manipulator_moveit_real_4.png

TurtleBot3 Waffle with Open-Manipulator
-----------

Install dependent packages for the Open-Manipulator.

.. code-block:: bash

  cd ~/catkin_ws/src
  git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
  cd ~/catkin_ws && catkin_make

Below command will load the TurtleBot3 Waffle with Open-Manipulator on Rviz.

.. code-block:: bash

  roslaunch open_manipulator_with_tb3 open_manipulator_chain_with_tb3_rviz.launch

.. image:: _static/manipulation/TurtleBot3_with_Open_Manipulator.png
