.. _chapter_opencr_software_setup:

OpenCR Software Setup
=====================

.. image:: _static/software/remote_pc_and_turtlebot.png
    :align: center

.. WARNING:: The contents in this chapter corresponds to the ``Remote PC`` (your desktop or laptop PC) which will control TurtleBot3. Do **NOT** apply this instruction to your TurtleBot3.

.. NOTE:: OpenCR is pre-loaded with the software needed to run your specific TurtleBot3 model(Burger or Waffle). Refer to the information below only if you want to modify the existing software or write new software for OpenCR.

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame`` and OpenCR software setup can be done from Intel® Joule™.

OpenCR controls DYNAMIXELs with instructions from the SBC. To be able to control DYNAMIXELs, a specific firmware should be installed on the board. See the descriptions and configure the settings.

ArduinoIDE Settings for OpenCR
----------------------------------

Following instructions will setup OpenCR Arduino development environment on the ``Remote PC``.

USB Port Settings
~~~~~~~~~~~~~~~~~

.. TIP:: The terminal application can be found with the Ubuntu search icon on the top left corner of the screen. Shortcut key for terminal is Ctrl-Alt-T.

[``Remote PC``] The following commands allow to use OpenCR USB port for uploading ``Arduino IDE`` program without acquiring root permission.

.. code-block:: bash

  wget https://raw.githubusercontent.com/ROBOTIS-GIT/OpenCR/master/99-opencr-cdc.rules
  sudo cp ./99-opencr-cdc.rules /etc/udev/rules.d/
  sudo udevadm control --reload-rules
  sudo udevadm trigger

.. image:: _static/preparation/7_1_1_usb_port_setting.png

Compiler Settings
~~~~~~~~~~~~~~~~~

[``Remote PC``] OpenCR libraries are designed for 32-bit platform, therefore, 64-bit PC requires 32-bit compiler for Arduino IDE.

.. code-block:: bash

  sudo apt-get install libncurses5-dev:i386
  
.. image:: _static/preparation/7_1_2_compiler_settings.png


Install Arduino IDE
~~~~~~~~~~~~~~~~~~~~~~~

[``Remote PC``] Download the latest version of ``Arduino IDE`` from official Arduino homepage and install the program. OpenCR supports Arduino IDE ``1.6.12`` or later (OpenCR has also been tested with Arduino IDE ``1.8.1``.).

https://www.arduino.cc/en/Main/Software

[``Remote PC``] Extract downloaded file to desired folder and execute the install file in the folder from the terminal. The below example uses *tools* folder in the root directory (``~/``). This folder will act as Arduino IDE folder.

.. code-block:: bash

  cd ~/tools/arduino-1.8.1
  ./install.sh

[``Remote PC``] Open the script file with below command.

.. code-block:: bash

  gedit ~/.bashrc

[``Remote PC``] Append below ``Arduino IDE`` path information at the end of the ``bashrc`` file. It is recommended to use **gedit editor**. (Use another editor if necessary)

.. code-block:: bash

  export PATH=$PATH:$HOME/tools/arduino-1.8.1

[``Remote PC``] Last but not least, `source` the ``bashrc`` file to apply changes.

.. code-block:: bash

  source ~/.bashrc

Run Arduino IDE
~~~~~~~~~~~~~~~~~~~

[``Remote PC``] In order to run ``Arduino IDE`` on Linux platform, enter below command on the terminal.

.. code-block:: bash

  arduino

[``Remote PC``] If the program is installed and configured correctly, you'll be able to see GUI program as below.

.. image:: _static/preparation/ide0.png

Porting OpenCR to Arduino IDE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Preferences
...........

[``Remote PC``] When ``Arduino IDE`` is running, go to ``File`` → ``Preferences`` from the menu of the program. When the *Preferences* window appears, copy and paste following link to the ``Additional Boards Manager URLs`` textbox. (This step may take about 20 min.)

.. code-block:: bash

  https://raw.githubusercontent.com/ROBOTIS-GIT/OpenCR/master/arduino/opencr_release/package_opencr_index.json

.. image:: _static/preparation/ide1.png

Install OpenCR Package from Boards Manager
.............................................

[``Remote PC``] Go to ``Tools`` → ``Board`` → ``Boards Manager``.

.. image:: _static/preparation/ide2.png

[``Remote PC``] Type `OpenCR` into the textbox to find the ``OpenCR by ROBOTIS`` package. If the package is found, click ``Install``.

.. image:: _static/preparation/ide3.png

[``Remote PC``] When the package installation is completed, "INSTALLED" text will be appeared next to the package name.

.. image:: _static/preparation/ide4.png

[``Remote PC``] See if ``OpenCR Board`` is now in the list of ``Tools`` → ``Board``. Select ``OpenCR Board`` to import OpenCR Board source.

.. image:: _static/preparation/ide5.png

Port Setting
............

[``Remote PC``] This section shows how to setup the USB port for program upload. OpenCR should be connected to the PC with the USB port.
 
[``Remote PC``] Select ``Tools`` → ``Port`` → ``/dev/ttyACM0``.

.. WARNING:: The last digit value `0` in the string ``/dev/ttyACM0`` might be different depend on the USB connection environment.

.. image:: _static/preparation/ide6.png

Writing Bootloader (can be skipped)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. NOTE:: This section is not necessary until there is new updates in the OpenCR bootloader. Once the bootloader is burned on the board, IT DOESN'T NEED EXTRA BURNING.

The STM32F7xx, which is used for the main MCU of OpenCR, supports DFU(Device Firmware Upgrade). This enables built-in bootloader of the MCU to boot with the DFU protocol by using USB, primarily for the bootloader initialization, the recovery mode and the bootloader update. The biggest advantage of using bootloader with USB is that JTAG equipment is not required. Therefore, writing the new firmware by using the DFU mode which is embedded in the MCU will not require writing / debugging equipment such as STLink.

Programmer Setting
..................

[``Remote PC``] Go to ``Tools`` → ``DFU-UTIL``

.. image:: _static/preparation/ide7.png

Entering the DFU Mode
.....................

[``Remote PC``] Press ``Reset`` button while ``Boot`` button is pressed. This enables user to activate the DFU mode.

.. image:: _static/preparation/opencr_button_for_dfu.png

[``Remote PC``] If you successfully entered to DFU mode, you will be able to find ``STMicroelectronics STM Device in DFU Mode`` text string when *lsusb* is entered in the terminal.

.. image:: _static/preparation/ide10.png

Download the Bootloader
.......................

[``Remote PC``] Go to ``Tools`` → ``Burn Bootloader`` to download the bootloader.

.. image:: _static/preparation/ide9.png

[``Remote PC``] When download is completed, press ``Reset`` button again.

OpenCR Firmware Settings for ROS
--------------------------------

Add TurtleBot3 Firmware to OpenCR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

OpenCR firmware (or the source) for ROS is to control DYNAMIXEL and sensors in the ROS. The firmware is located in OpenCR example which is downloaded by the board manager.
If you have TurtleBot3 Burger,

[``Remote PC``] Go to ``File`` → ``Examples`` → ``turtlebot3`` → ``turtlebot3_burger`` → ``turtlebot3_core``.

If you have TurtleBot3 Waffle,

[``Remote PC``] Go to ``File`` → ``Examples`` → ``turtlebot3`` → ``turtlebot3_waffle`` → ``turtlebot3_core``.

.. image:: _static/opencr/o1.png

[``Remote PC``] Click ``Upload`` button to upload the firmware to OpenCR.

.. image:: _static/opencr/o2.png

.. image:: _static/opencr/o3.png

.. NOTE:: If error occurs while uploading firmware, go to ``Tools`` → ``Port`` and check if correct port is selected. Press ``Reset`` button on the OpenCR and try to upload the firmware again.

[``Remote PC``] When firmware upload is completed, ``jump_to_fw`` text string will be printed on the screen.

.. _ROS: http://wiki.ros.org
