.. _chapter_pc_software_setup:

PC Software Setup
=================

.. image:: _static/software/remote_pc_and_turtlebot.png
    :align: center

.. WARNING:: The contents in this chapter corresponds to the ``Remote PC`` (your desktop or laptop PC) which will control TurtleBot3. Do NOT apply this instruction to your TurtleBot3.

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame``.

Install Ubuntu on Remote PC (Desktop or Laptop PC)
-----------------------------------------------------------

[``Remote PC``] Download ``Ubuntu 16.04`` on the remote PC from the following link.

- https://www.ubuntu.com/download/desktop

If you need more help for installing Ubuntu, check out the step-by-step guide from the link below.

- https://www.ubuntu.com/download/desktop/install-ubuntu-desktop

Install ROS on Remote PC
--------------------------------

.. image:: _static/logo_ros.png
    :align: center
    :target: http://wiki.ros.org

[``Remote PC``] There are two ways to install `ROS`_. If you prefer manual installation, please take the second method.
In order to develop source code from the remote PC, please configure ROS environment after completing ROS installation. 

First Method
~~~~~~~~~~~~

Install `ROS`_ by using a simple installation script file

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

.. code-block:: bash

  sudo apt-get update
  sudo apt-get upgrade
  wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh && chmod 755 ./install_ros_kinetic.sh && bash ./install_ros_kinetic.sh

Second Method
~~~~~~~~~~~~~

You can start from "`1.2 Setup your sources.list`_" and keep following the instruction until "`1.7 Getting rosinstall`_" from below ROS installation instruction link.

- http://wiki.ros.org/kinetic/Installation/Ubuntu

.. NOTE:: In order to check which packages are installed, please check this link out. https://raw.githubusercontent.com/oroca/oroca-ros-pkg/kinetic/ros_install.sh

Configure ROS Environment
~~~~~~~~~~~~~~~~~~~~~~~~~
If you are going to modify or develop source code from the remote PC, you'll have to configure ROS environment. Simple instructions are described in the below link and it will take a couple minutes.

- http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment

Install dependent packages
--------------------------

[``Remote PC``] The next step is to install dependent packages for TurtleBot3 control.

.. code-block:: bash

  sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python ros-kinetic-rosserial-server ros-kinetic-rosserial-client ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro ros-kinetic-compressed-image-transport ros-kinetic-rqt-image-view ros-kinetic-gmapping ros-kinetic-navigation

.. code-block:: bash

  cd ~/catkin_ws/src/
  git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
  git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
  cd ~/catkin_ws && catkin_make

If catkin_make command is completed without any errors, the preparation for TurtleBot3 is done.


Network Configuration
---------------------

.. image:: _static/software/network_configuration.png

ROS requires IP addresses in order to communicate between TurtleBot3 and the remote PC.

[``Remote PC``] Enter the below command on the terminal window of the remote PC to find out the IP address of the remote PC.

.. code-block:: bash

  ifconfig

Text strings in the rectangle is the IP address of the ``Remote PC``.

.. image:: _static/software/network_configuration2.png

[``Remote PC``] Enter the below command.

.. code-block:: bash

  gedit ~/.bashrc

Modify the address of `localhost` with the IP address acquired from the above terminal window.

.. image:: _static/software/network_configuration3.png

[``Remote PC``] Then, source the bashrc with below command.

.. code-block:: bash

  source ~/.bashrc


.. _1.2 Setup your sources.list: http://wiki.ros.org/kinetic/Installation/Ubuntu#Installation.2BAC8-Ubuntu.2BAC8-Sources.Setup_your_sources.list
.. _1.7 Getting rosinstall: http://wiki.ros.org/kinetic/Installation/Ubuntu#Getting_rosinstall
.. _ROS: http://wiki.ros.org
