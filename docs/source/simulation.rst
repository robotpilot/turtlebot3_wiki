.. _chapter_simulation:

Simulation
==========

.. image:: _static/software/remote_pc_and_turtlebot.png
    :align: center

.. WARNING:: The contents in this chapter corresponds to the ``Remote PC`` (your desktop or laptop PC) which will control TurtleBot3. Do NOT apply this instruction to your TurtleBot3.

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame``.

TurtleBot3 Fake Node Implementation
-----------------------------------

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

Install dependent packages for the TurtleBot3 Simulation.

.. code-block:: bash

  cd ~/catkin_ws/src/
  git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
  cd ~/catkin_ws && catkin_make

``TurtleBot3 fake node`` is a very simple simulation node that can be run without having an actual robot. You can control the virtual TurtleBot3 in RViz with a teleop node.

.. code-block:: bash

  export TURTLEBOT3_MODEL=burger
  roslaunch turtlebot3_fake turtlebot3_fake.launch

.. code-block:: bash

  roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/iHXZSLBJHMg" frameborder="0" allowfullscreen></iframe>

|

Stage (2D)
----------

(TODO)

Gazebo (3D)
-----------

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/xXM5r_SVkWM" frameborder="0" allowfullscreen></iframe>

|

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

.. WARNING:: If you are running Gazebo for the first time on your ``Remote PC``, it usually takes a bit longer.

Before launching Gazebo simulation with TurtleBot3, ``TurtleBot3 model files`` should be copied into ``gazebo model folder``.

.. code-block:: bash
  
  mkdir ~/.gazebo/
  mkdir ~/.gazebo/models/
  cp -r  ~/catkin_ws/src/turtlebot3_simulations/turtlebot3_gazebo/worlds/turtlebot3 ~/.gazebo/models/

Set Turtlebot3 model. Select either burger or waffle for the model parameter in the below command.

.. code-block:: bash

  export TURTLEBOT3_MODEL=burger

Below command will load the TurtleBot3 on the default Gazebo environment ``TurtleBot3 empty world``.

.. code-block:: bash

  roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch

.. image:: _static/simulation/turtlebot3_empty_world.png

The TurtleBot3 can be driven with a keyboard by launching teleoperation with below command.

.. code-block:: bash

  roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

``TurtleBot3 world`` is a map consists of simple objects that makes up the shape of TurtleBot3 symbol.
  
.. code-block:: bash

  roslaunch turtlebot3_gazebo turtlebot3_world.launch

.. image:: _static/simulation/turtlebot3_world_bugger.png

.. image:: _static/simulation/turtlebot3_world_waffle.png

The TurtleBot3 can freely move in the TurtleBot3 world.

.. code-block:: bash

  export TURTLEBOT3_MODEL=burger
  roslaunch turtlebot3_gazebo turtlebot3_simulation.launch

RViz shows published topics when simulation is launched.

.. code-block:: bash

  export TURTLEBOT3_MODEL=burger
  roslaunch turtlebot3_gazebo turtlebot3_gazebo_rviz.launch

.. image:: _static/simulation/turtlebot3_gazebo_rviz.png
