.. _chapter_sbc_software_setup:

SBC Software Setup
==================

.. image:: _static/software/remote_pc_and_turtlebot.png
    :align: center

.. NOTE:: An ``SBC(Single-Board Computer)`` is a complete computer built on a single circuit board with microprocessor(s), memory, input/output (I/O) and other features required as a fully functional computer. TurtleBot3 uses Raspberry Pi (TB3 Burger) and Intel® Joule™ (TB3 Waffle) as SBC.

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame``.

Install Linux on TurtleBot3 Burger (Raspberry Pi 3)
---------------------------------------------------------

.. WARNING:: The SDcard should have at least **8 GB** of empty space in order to install Linux on TurtleBot3.

[``Remote PC``] Download ``Ubuntu MATE 16.04`` on the Raspberry Pi 3 from the link below.

- https://ubuntu-mate.org/download/

.. image:: _static/preparation/download_ubuntu_mate_image.png

[``Remote PC``] In order to install Ubuntu MATE from an image file, it is recommended using GNOME Disks with ``Restore Disk Image…`` option, which natively supports XZ compressed image.

.. code-block:: bash

  sudo apt-get install gnome-disk-utility

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/V_6GNyL6Dac?ecver=1" frameborder="0" allowfullscreen></iframe>

|

.. TIP:: It is recommended using ``GNOME Disks``, but other applications such as ``ddrescue`` on Linux can be used.

  .. code-block:: bash

    sudo apt-get install gddrescue xz-utils
    unxz ubuntu-mate-16.04.2-desktop-armhf-raspberry-pi.img.xz
    sudo ddrescue -D --force ubuntu-mate-16.04.2-desktop-armhf-raspberry-pi.img /dev/sdx

.. TIP:: It is recommended using ``GNOME Disks``, but other applications such as ``Win32 Disk Imager`` on Windows can be used.

  https://sourceforge.net/projects/win32diskimager/

Install Linux on TurtleBot3 Waffle (Intel® Joule™)
-------------------------------------------------------

In this section, the Alternative Ubuntu Desktop 16.04 LTS will be installed on Intel® Joule™.

[``Remote PC``] Download Ubuntu image ``Alternative Ubuntu 16.04 for Intel® Joule™`` from the below link.

- http://people.canonical.com/~platform/snappy/tuchuck/desktop-final/tuchuck-xenial-desktop-iso-20170317-0.iso

[``Remote PC``] In order to make a bootable installation USB drive, please follow the `Alternative install(Ubuntu Desktop 16.04 LTS)`_ section from the below link.

- https://developer.ubuntu.com/core/get-started/intel-joule

[``Remote PC``] Before getting started, Joule requires a BIOS update to install Ubuntu Image. Download the latest software which contains Joule's new BIOS and flash the BIOS into the Joule by following instructions below.

- https://software.intel.com/en-us/flashing-the-bios-on-joule

.. WARNING:: ``Intel® Joule™`` comes with ``passive heatsink`` in the package. It is recommended to use the heatsink. In order to operate Joule without the heatsink, please follow the extra instruction: https://software.intel.com/en-us/node/721471

[``Intel® Joule™``] Connect ``micro HDMI to HDMI cable``, ``power connector supplied by OpenCR``, ``USB devices`` including ``Bootable USB drive``, ``mouse`` and ``keyboard``. You might need a USB hub to plug multiple USB devices into Joule.

[``Intel® Joule™``] Installation will be proceeded as shown in below images. When Joule is turned on, monitor will blink about 3 times after 5 seconds, and print menu screen. Press ``F7`` to go to ``Boot Manager``.

.. image:: _static/preparation/j1.JPG

[``Intel® Joule™``] Select ``USB Device``.

.. image:: _static/preparation/j2.JPG

.. image:: _static/preparation/j3.JPG

.. image:: _static/preparation/j4.JPG

.. image:: _static/preparation/j5.JPG

[``Intel® Joule™``] Select ``Erase disk and install Ubuntu`` then ``continue``.

.. image:: _static/preparation/j6.JPG

[``Intel® Joule™``] ``Intel® Joule™`` has two different disk drives: 16GB micro SD Card and 16GB eMMC. In this instruction, it is highly recommended to install ``Alternarive Ubuntu for Joule`` on the ``16GB eMMC``. Select ``MMC/SD card #2 (mmcblk1) - 15.7 GB MMC 016G32`` then ``continue``.

.. image:: _static/preparation/j7.JPG

.. image:: _static/preparation/j8.JPG

[``Intel® Joule™``] Installation will take about 10 minutes.

.. image:: _static/preparation/j9.JPG

[``Intel® Joule™``] When installation is completed, click ``Restart Now``.

.. image:: _static/preparation/j10.JPG

[``Intel® Joule™``] Remove bootable USB drive from Joule.

.. image:: _static/preparation/j11.JPG

[``Intel® Joule™``] Don't press any key. It will boot from ``16GB eMMC`` which is a default boot device.

.. image:: _static/preparation/j12.JPG

.. image:: _static/preparation/j13.JPG

.. image:: _static/preparation/j14.JPG

[``Intel® Joule™``] Finish the rest of settings.

.. image:: _static/preparation/j15.JPG

.. image:: _static/preparation/j16.JPG

.. image:: _static/preparation/j17.JPG

.. image:: _static/preparation/j18.JPG

.. image:: _static/preparation/j19.JPG

.. image:: _static/preparation/j20.JPG

.. image:: _static/preparation/j21.JPG




Install ROS and Packages (Burger and Waffle)
------------------------------------------------

.. WARNING:: The contents in this chapter corresponds to the SBC of ``TurtleBot3`` (Raspberry Pi 3 or Intel® Joule™) which will be the main computer of TurtleBot3. Do **NOT** apply this instruction to your Remote PC (your desktop PC or laptop).

.. NOTE:: This instruction takes about 2 hours to install ROS and TurtleBot3 related packages. Elapsed time may vary depend on network environment.

.. image:: _static/logo_ros.png
    :align: center
    :target: http://wiki.ros.org

[``TurtleBot``] There are two ways to install `ROS`_. If you prefer manual installation, please take the second method.

First Method
~~~~~~~~~~~~
[``TurtleBot``] Install `ROS`_ by using a simple installation script file.

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

[``TurtleBot Burger``]

.. code-block:: bash

  sudo apt-get update
  sudo apt-get upgrade
  wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic_rp3.sh && chmod 755 ./install_ros_kinetic_rp3.sh && bash ./install_ros_kinetic_rp3.sh

[``TurtleBot Waffle``]

.. code-block:: bash

  sudo apt-get update
  sudo apt-get upgrade
  wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh && chmod 755 ./install_ros_kinetic.sh && bash ./install_ros_kinetic.sh
  
.. NOTE:: After install ROS, please reboot Raspberry Pi or Intel® Joule™.

Second Method
~~~~~~~~~~~~~
[``TurtleBot``] You can start from "`1.2 Setup your sources.list`_" and keep following the instruction until "`1.7 Getting rosinstall`_" from below ROS installation instruction link.

- http://wiki.ros.org/kinetic/Installation/Ubuntu

.. NOTE:: In order to see which packages are installed, please check this link out. https://raw.githubusercontent.com/oroca/oroca-ros-pkg/kinetic/ros_install.sh

Install Dependent Packages
~~~~~~~~~~~~~~~~~~~~~~~~~~
[``TurtleBot``] The next step is to install dependent packages for TurtleBot3 control.

.. code-block:: bash

  sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python ros-kinetic-rosserial-server ros-kinetic-rosserial-client ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro ros-kinetic-compressed-image-transport ros-kinetic-rqt-image-view ros-kinetic-gmapping ros-kinetic-navigation

.. code-block:: bash

  cd ~/catkin_ws/src
  git clone https://github.com/ROBOTIS-GIT/hls_lfcd_lds_driver.git
  git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
  git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
  cd ~/catkin_ws && catkin_make

If catkin_make command is completed without any errors, the preparation for TurtleBot3 is done.

USB Settings (Burger and Waffle)
--------------------------------

[``TurtleBot``] The following commands allow to use USB port for OpenCR without acquiring root permission.

.. code-block:: bash

  cd ~/catkin_ws/src/turtlebot3
  sudo cp ./99-turtlebot3-cdc.rules /etc/udev/rules.d/
  sudo udevadm control --reload-rules
  sudo udevadm trigger

Network Configuration (Burger and Waffle)
-----------------------------------------

.. image:: _static/software/network_configuration.png

ROS requires IP addresses in order to communicate between TurtleBot3 and remote PC.

[``TurtleBot``] Enter the below command on the terminal window of the SBC in TurtleBot3 to find out the IP address of TurtleBot3.

.. code-block:: bash

  ifconfig

Texts in the rectangle is the IP address of the ``TurtleBot``.

.. image:: _static/software/network_configuration4.png

[``TurtleBot``] Enter the following command.

.. code-block:: bash

  gedit ~/.bashrc

[``TurtleBot``] Replace the `localhost` in the ROS_MASTER_URI address with the IP address acquired from `Remote PC Network Configuration`_. Also replace the `localhost` in the ROS_HOSTNAME address with the IP address acquired from the above terminal window, which is the IP address of TurtleBot3.

.. image:: _static/software/network_configuration5.png

[``TurtleBot``] Then, source the bashrc with below command.

.. code-block:: bash

  source ~/.bashrc


.. _Alternative install(Ubuntu Desktop 16.04 LTS): https://developer.ubuntu.com/core/get-started/intel-joule#alternative-install:-ubuntu-desktop-16.04-lts
.. _1.2 Setup your sources.list: http://wiki.ros.org/kinetic/Installation/Ubuntu#Installation.2BAC8-Ubuntu.2BAC8-Sources.Setup_your_sources.list
.. _1.7 Getting rosinstall : http://wiki.ros.org/kinetic/Installation/Ubuntu#Getting_rosinstall
.. _Remote PC Network Configuration: http://turtlebot3.robotis.com/en/latest/pc_software.html#network-configuration
.. _ROS: http://wiki.ros.org
