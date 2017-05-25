.. _chapter_applications:

Applications
============

This chapter shows some demos using Turtlebot3.
In order to implement these demos, you have to install the turtlebot3_applications package.

.. NOTE:: The Turtlebot3 has been tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame``.

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

[``Remote PC``] Go to  ROS source directory (/home/<user_name>/catkin_ws/src) and clone the turtlebot3_applications repository.

.. code-block:: bash

  cd ~/catkin_ws/src
  git clone https://github.com/ROBOTIS-GIT/turtlebot3_applications.git

[``Remote PC``] catkin_make to install the new package

.. code-block:: bash

 cd ~/catkin_ws && catkin_make


TurtleBot Follower Demo
-----------------------

(TODO)

TurtleBot Panorama Demo Using Raspberry Pi Camera Module
--------------------------------------------------------

.. NOTE:: The turtlebot3_panorama demo uses pano_ros for taking snapshots and stitching them together to create panoramic image.
.. NOTE:: Panorama Demo requires to install Raspicam package. Instructions for installing this package can be found at https://github.com/UbiquityRobotics/raspicam_node
.. NOTE:: Panorama Demo requires to install OpenCV and cvbridge packages. Instructions for installing OpenCV can be found at http://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html

[``TurtleBot``] Launch the Raspberry Pi cam V2

.. code-block:: bash

  roslaunch raspicam_node camerav2_1280x960.launch

[``Remote PC``] Launch Panorama

.. code-block:: bash

  roslaunch turtlebot3_panorama panorama.launch

[``Remote PC``] To start the panorama demo

.. code-block:: bash

  rosservice call turtlebot3_panorama/take_pano 0 360.0 30.0 0.3


Parameters that can be sent to the rosservice to get a panoramic image are:

- mode for taking the pictures. Can be:
    0 for snap&rotate (i.e. rotate, stop, snapshot, rotate, stop, snapshot, ...)
    1 for continuous (i.e. keep rotating while taking snapshots)
    2 to stop taking pictures and create panoramic image
- total angle of panoramic image, in degrees
- angle interval (in degrees) when creating the panoramic image in snap&rotate mode, time interval (in seconds) otherwise
- rotating velocity (in radians/s)


[``Remote PC``] To view the results

.. code-block:: bash

  rqt_image_view image:=/turtlebot3_panorama/panorama


.. image:: _static/application/panorama_view.png

Automatic Docking
-----------------

(TODO)
