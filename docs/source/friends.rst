.. _chapter_friends:

Friends
=======

In the video, watch how TurtleBot3 can be assembled and reassembled with a few additional parts. The waffle plate which is the biggest part among TurtleBot3 components can be assembled in various sizes and shapes, thanks to its diverse holes for bolts and nuts.

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/o9d7NVC0A1Y" frameborder="0" allowfullscreen></iframe>

|

With this extendible component, handful of TurtleBot3 friends with various characteristics could be built. You can create a totally new robot that is never seen before.

TurtleBot3 Friends List:

- :ref:`TurtleBot3 Friends: Car<section_car>`
- :ref:`TurtleBot3 Friends: OpenManipulator Chain<section_openmanipulator_chain>`
- :ref:`TurtleBot3 Friends: Segway<section_segway>`
- :ref:`TurtleBot3 Friends: Conveyor<section_conveyor>`
- :ref:`TurtleBot3 Friends: Monster<section_monster>`
- :ref:`TurtleBot3 Friends: Tank<section_tank>`
- :ref:`TurtleBot3 Friends: Omni<section_omni>`
- :ref:`TurtleBot3 Friends: Mecanum<section_mecanum>`
- :ref:`TurtleBot3 Friends: Bike<section_bike>`
- :ref:`TurtleBot3 Friends: Road Train<section_road_train>`
- :ref:`TurtleBot3 Friends: Real TurtleBot<section_real_turtleBot>`
- :ref:`TurtleBot3 Friends: Carrier<section_carrier>`

.. image:: _static/friends/All_friends.jpg

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/gI0T4-aqTpI" frameborder="0" allowfullscreen></iframe>

|

Get source codes and make friends! Go to ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends``.

.. image:: _static/friends/ide.png

.. NOTE:: Any suggestions and ideas for TurtleBot3 Friends Project are always welcomed. Tell us about your creative TurtleBot3 Friends. We can introduce your friend to the world through this wiki page! :)

:E-Mail: ost@robotis.com

.. _section_car:

TurtleBot3 Friends: Car
------------------------

:``Type``: RC Car
:``Features``: About 1:2 gear ratio, differential gears want to make Car be in the Formula E!
:``Components``: Two Dynamixel X 430 Series (One for steering, one for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, OLLO plastic frames.
:``Hardware``: Due to the complex hardware configuration, it will be released as a later improved version. :)
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_car``
:``Video``:

.. _section_auto:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/IkPexspUgKk" frameborder="0" allowfullscreen></iframe>

|

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/1V33iEu4ylw" frameborder="0" allowfullscreen></iframe>

|

.. _section_openmanipulator_chain:

TurtleBot3 Friends: OpenManipulator Chain
-----------------------------------------

.. image:: _static/friends/friends_open_manipulator_waffle.png

:``Type``: Manipulator 4 DOF + 1 Gripper
:``Features``: Compatible with TurtleBot3 Waffle and it has linear gripper for pick and place.
:``Components``: Four Dynamixel X 430 Series (Four for joints, one for gripper), an OpenCR1.0 Board, 3D printed chassis.
:``BOM``: Please refer to the `OpenManipulator Wiki`_
:``Hardware``: https://goo.gl/xgxh2G (TB3 Waffle + OpenManipulator Chain)
:``Hardware``: https://goo.gl/Wv3KON (OpenManipulator Chain)
:``Software``: https://github.com/ROBOTIS-GIT/open_manipulator (We are preparing for OpenCR Example)
:``Video``:

.. _OpenManipulator Wiki: https://github.com/ROBOTIS-GIT/open_manipulator/wiki/OpenManipulator-Chain

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/Qhvk5cnX2hM" frameborder="0" allowfullscreen></iframe>

|

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/qbht0ssv8M0" frameborder="0" allowfullscreen></iframe>

|

.. _section_segway:

TurtleBot3 Friends: Segway
--------------------------

.. image:: _static/friends/friends_segway.png

:``Type``: Segway robot
:``Features``: Balancing with only two DYNAMIXEL by applying PID controller.
:``Components``: Two Dynamixel X 430 Series (All for balancing), an OpenCR1.0 Board, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/rbmqLB
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_segway``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/VAY-0xBOE2g" frameborder="0" allowfullscreen></iframe>

|

.. _section_conveyor:

TurtleBot3 Friends: Conveyor
----------------------------

.. image:: _static/friends/friends_conveyor.png

:``Type``: 4 Wheel parallel translation vehicle
:``Features``: 4 Joints and 4 wheels will become a futuristic technology on transportation society by overcoming fuel-consuming mechanics.
:``Components``: Eight Dynamixel X 430 Series (Four for steering, four for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/HSSqp7
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_conveyor``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/uv2faO7GhXc" frameborder="0" allowfullscreen></iframe>

|

.. _section_monster:

TurtleBot3 Friends: Monster
---------------------------

.. image:: _static/friends/friends_monster.png

:``Type``: 4WD Car
:``Features``: 4 Big wheels let it be strong in the rough terrain or even a big difference of elevation.
:``Components``: Four Dynamixel X 430 Series (All for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/oW8UXY
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_monster``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/UqdwGLH1-cA" frameborder="0" allowfullscreen></iframe>

|

.. _section_tank:

TurtleBot3 Friends: Tank
------------------------

.. image:: _static/friends/friends_tank.png

:``Type``: Caterpillar
:``Features``: Caterpillar units which are connected and assembled on sprocket wheels make it be strong in the rough terrain.
:``Components``: Two Dynamixel X 430 Series (All for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, Caterpillar Unit, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/M722Ff
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_tank``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/vndnwpVEpVE" frameborder="0" allowfullscreen></iframe>

|

.. _section_omni:

TurtleBot3 Friends: Omni
------------------------

.. image:: _static/friends/friends_omni.png

:``Type``: Omni wheel
:``Features``: Omni wheels have additional discs around the circumference make it laterally driveable.
:``Components``: Three Dynamixel X 430 Series (All for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/2LBJik
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_omni``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/r8wRACM_ZbE" frameborder="0" allowfullscreen></iframe>

|

.. _section_mecanum:

TurtleBot3 Friends: Mecanum
---------------------------

.. image:: _static/friends/friends_mecanum.png

:``Type``: Mecanum wheel
:``Features``: Mecanum wheels have additional discs around the circumference make it laterally driveable.
:``Components``: Four Dynamixel X 430 Series (All for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/3aTdg9
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_mechanum``
:``Video``: See in the video :ref:`Friends-Omni<omni>` above.

.. _section_bike:

TurtleBot3 Friends: Bike
------------------------

.. image:: _static/friends/friends_bike.png

:``Type``: 3-DOF Motorcycle
:``Features``: Cute 3-wheeled bikey reveals its existence on the "Car" film as a brother of the "Car".
:``Components``: Three Dynamixel X 430 Series (One for steering, two for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/JMntH1
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_bike``
:``Video``: See in the videos :ref:`Friends-Auto<section_auto>` and :ref:`Friends-Monster<section_monster>` above.

.. _section_road_train:

TurtleBot3 Friends: Road Train
------------------------------

.. image:: _static/friends/friends_road_train.png

:``Type``: Road train
:``Features``: Road train can connect vehicles and it can serve various things! 
:``Components``: Two Dynamixel XM-430 Series (two for driving), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/fsH5L2
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_road_train``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/uhkq1w4YoEE" frameborder="0" allowfullscreen></iframe>

|

.. _section_real_turtlebot:

TurtleBot3 Friends: Real TurtleBot
----------------------------------

.. image:: _static/friends/friends_real.png

:``Type``: 8-DOF legged robot (a.k.a. Real TurtleBot)
:``Features``: A real TurtleBot will make most of the fanpics in the turtlebot society!.
:``Components``: Ten Dynamixel X 430 Series (Four for leg joint, another four for shoulder joint, two for head), an OpenCR1.0 Board, a RC100 Remote Controller with BT410 master-slave Bluetooth modules, TurtleBot3 Chassis and Battery, 3D printed chassis.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/wtcHxE
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_friends`` → ``turtlebot3_realturtlebot``
:``Video``:

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/KNWkAe0ob9g" frameborder="0" allowfullscreen></iframe>

|

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/vort-z9HDlU" frameborder="0" allowfullscreen></iframe>

|

.. _section_carrier:

TurtleBot3 Friends: Carrier
----------------------------

.. image:: _static/friends/friends_carrier.png

:``Type``: 2 Wheel mobile based platform as service robot
:``Features``: 2 wheeled mobile platform will serve whatever you wants.
:``Components``: A TurtleBot3 Waffle, 6 supports for 4th layer, another 6 supports for 5th layer construction, extra Waffle Plates in each layers, customized 3D printed wheel and ball caster.
:``BOM``: https://goo.gl/XPgJkZ
:``Hardware``: https://goo.gl/bXzBTJ
:``Software``: ``Examples`` → ``turtlebot3`` → ``turtlebot3_waffle`` → ``turtlebot3_waffle``
:``Video``:

.. raw:: html
