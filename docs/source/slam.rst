.. _chapter_slam:

SLAM
====

.. NOTE:: This instruction was tested on ``Ubuntu 16.04`` and ``ROS Kinetic Kame`` version.

.. WARNING:: Make sure that the step :ref:`[Bringup]<chapter_bringup>` was carried on previously to follow the instructions.

.. TIP:: Here recommends to use the joystick pad instead of the keyboard, because of its operability.

The Simultaneous Localization and Mapping, or SLAM, is a technique to draw a map by estimating the current position in virtual space while searching the areas in the arbitrary space.

The SLAM technique is a typical function of the TurtleBot3, and is a class of the Turtlebot brand. A video here shows how much accurately the TurtleBot3 can draw the map, even if it is a small, cheap robot platform.

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/lkW4-dG2BCY" frameborder="0" allowfullscreen></iframe>

|

:Date: 2016.11.29
:Robot: TurtleBot3 Burger model
:Sensor: Laser Distance Sensor
:Packages: Gmapping / Cartographer
:Place: ROBOTIS Labs & HQ, 15th-floor corridor
:Duration: 55 minutes
:Distance: Total 351 meters

.. raw:: html

  <iframe width="640" height="360" src="https://www.youtube.com/embed/7mEKrT_cKWI" frameborder="0" allowfullscreen></iframe>

|

:Date: 2017.04.20
:Robot: TurtleBot3 Burger model and Waffle model
:Sensor: Laser Distance Sensor
:Packages: Gmapping
:Place: ROBOTIS HQ Education Room
:Duration: About 4 minutes
:Distance: Total 15 meters

Create a map through the teleoperation
------------------------------

.. TIP:: Terminal is opened to go to the Ubuntu search icon, type "Terminal" or use Ctrl-Alt-T.

[``Remote PC``] Open a terminal, then run the SLAM launch file.

.. code-block:: bash

  export TURTLEBOT3_MODEL=burger
  roslaunch turtlebot3_slam turtlebot3_slam.launch

If your robot is TurtleBot3 Waffle,

.. code-block:: bash

  export TURTLEBOT3_MODEL=waffle
  roslaunch turtlebot3_slam turtlebot3_slam.launch


[``Remote PC``] Visualize the model by the RViz.

.. code-block:: bash

  rosrun rviz rviz -d `rospack find turtlebot3_slam`/rviz/turtlebot3_slam.rviz

[``Remote PC``] Teleoperation with Keyboard

.. code-block:: bash

  roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

Save the map to file
--------------------

[``Remote PC``] Open a terminal, then run map saver node.

.. code-block:: bash

  rosrun map_server map_saver -f ~/map

The files named as **map.pgm** and **map.yaml** will be built in the ``~/`` directory ($HOME directory, /home/<username>).
