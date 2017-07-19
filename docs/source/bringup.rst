.. _chapter_bringup:

Bringup
=======

.. image:: _static/software/remote_pc_and_turtlebot.png
    :align: center

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame``.

.. WARNING:: This instruction is intended to be run on the remote PC. If you are following the instruction on ``TurtleBot``, please do **NOT** run *roscore* command.

.. WARNING:: Make sure that IP address on each device is set correctly.

.. WARNING:: When the battery voltage is lower than 11V, the buzzer alarm will continuously sound and actuators will be disabled. The battery must be recharged when the buzzer alarm sounds.

.. TIP:: Before start bringup TurtleBot3, We recommend you add ``export`` command to ``bashrc`` depend on your TurtleBot3(``burger`` or ``waffle``)
  
  .. code-block:: bash

    getdit ~/.bashrc

  .. image:: _static/bringup/bashrc.png
    :align: center

  .. code-block:: bash

    source ~/.bashrc


Bringup TurtleBot3
----------------------

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

[``Remote PC``] Run roscore.

.. code-block:: bash

  roscore


TurtleBot3 Burger
~~~~~~~~~~~~~~~~~

[``TurtleBot``] Bring up basic packages to start TurtleBot3 applications.

.. code-block:: bash

  roslaunch turtlebot3_bringup turtlebot3_robot.launch

.. TIP::
  If you want to launch Lidar sensor and core separately, please use below commands.

  .. code-block:: bash

    roslaunch turtlebot3_bringup turtlebot3_lidar.launch
    roslaunch turtlebot3_bringup turtlebot3_core.launch

.. NOTE::
  If `lost sync with device` error message is displayed on the terminal window, the sensor device of TurtleBot3 might not be securely connected.

[``Remote PC``] Run RViz

.. code-block:: bash

  export TURTLEBOT3_MODEL=burger
  roslaunch turtlebot3_bringup turtlebot3_model.launch

.. image:: _static/bringup/rviz_burger_model.jpg

TurtleBot3 Waffle
~~~~~~~~~~~~~~~~~

[``TurtleBot``] Bring up basic packages to start TurtleBot3 applications.

.. code-block:: bash

  roslaunch turtlebot3_bringup turtlebot3_robot.launch

.. TIP::
  If you want to launch Lidar sensor, Intel® RealSense™ R200 and core separately, please use below commands.

  .. code-block:: bash

    roslaunch turtlebot3_bringup turtlebot3_lidar.launch
    roslaunch turtlebot3_bringup turtlebot3_realsense.launch
    roslaunch turtlebot3_bringup turtlebot3_core.launch

.. NOTE::
  If `lost sync with device` error message is displayed on the terminal window, sensor devices of the TurtleBot3 might not be securely connected.

[``Remote PC``] Run RViz

.. code-block:: bash

  export TURTLEBOT3_MODEL=waffle
  roslaunch turtlebot3_bringup turtlebot3_model.launch

.. image:: _static/bringup/rviz_waffle_model.jpg

In the next chapter, you will be able to test TurtleBot3 with various teleoperation methods.
