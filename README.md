# ROS-noetic-installtion


To install ROS noetic successfully on the virtual machine, you have to follow these steps:


## 1.	Download VirtualBox:

•	Visit the VirtualBox website: 

https://www.virtualbox.org/wiki/Downloads

•	Download the appropriate version for your operating system.



## 2.	Download Ubuntu 20.04 desktop image:

•	Choose either Ubuntu 20.04 LTS or Ubuntu MATE 20.04.

•	Download the image from the official Ubuntu website: 

https://releases.ubuntu.com/20.04 

•	 Make sure your computer meets the system requirements for the chosen Ubuntu version. Refer to the system requirements page for Ubuntu MATE:

https://ubuntu-mate.org/about/requirements/



## 3.	Create the virtual machine:

•	Open VirtualBox and click "New".

•	Enter a name for the virtual machine (e.g., "ROS Noetic").


•	Select the downloaded Ubuntu 20.04 image as the source.

•	Allocate at least 4 GB of RAM and 30 GB of hard disk space.


•	Follow the on-screen instructions to create the virtual machine.



## 4.	Start the virtual machine:

•	Click "Start" to boot the virtual machine.

•	You will be prompted to install Ubuntu 20.04. Follow the on-screen instructions.



## 5.	Install ROS noetic:

•	After installing Ubuntu 20.04, open a terminal window.

•	Update the package list:

```
sudo apt update
```

•	Add the ROS noetic repository:

```
sudo apt install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository multiverse
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo apt-add-repository "deb http://packages.ros.org/ros/ubuntu $(lsb_release -cs) main"
```
•	Update the package list again:

```
sudo apt update
```


•	Install ROS noetic:

```
sudo rosdep init rosdep update
```

•	Initialize ROSdep:

```
sudo rosdep init 
rosdep update
```

•	Source the setup file:

```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
 source ~/.bashrc
```



## 6.	Verify the installation:

•	Open a new terminal window and run the following command:

```
rosversion -d
```

 Now we can start using ROS noetic.
