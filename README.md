# rosqt45 - using ROS with Qt4 or Qt5

This is based on Daniel Stonier's excellent qt_ros package (http://wiki.ros.org/qt_ros) with some small modifications to support Qt5. Any bugs are probably due to my quick hack!

## Build
To clone and build,

    cd ~
    git clone git://github.com/richards-tech/rosqt45
    cd ~/rosqt45
    catkin_make

This will generate a Qt4 build. To use Qt5, set the QT5 parameter to 1:

    catkin_make -DQT5=1

Note that if switching between Qt versions, it is necessary to delete the build and devel directories - a catkin_make clean does not do everything required to change versions.

## Run
### qtalker and qlistener
Use a terminal window to start up roscore (if not already running):

    roscore

In another terminal window enter:

    cd ~/rosqt45
    source devel/setup.sh
    rosrun qt_tutorials qlistener

In another terminal window enter:

    cd ~/rosqt45
    source devel/setup.sh
    rosrun qt_tutorials qtalker

In both GUI windows, select to use environment variables and connect to the master.

### qadd_client and qadd_server
Use a terminal window to start up roscore (if not already running):

    roscore

In another terminal window enter:

    cd ~/rosqt45
    source devel/setup.sh
    rosrun qt_tutorials qadd_server

In another terminal window enter:

    cd ~/rosqt45
    source devel/setup.sh
    rosrun qt_tutorials qadd_client

In both GUI windows, select to use environment variables and connect to the master.
