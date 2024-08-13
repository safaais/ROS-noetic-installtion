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

 ## Now we can start using ROS noetic.

 # ROS-foxy-installtion

 To install ROS2 foxy, follow these steps:
 
## 1.	Set Locale:
•	Ensure your system has a locale that supports UTF-8.
•	If you're in a minimal environment, use the following commands:

```
locale # check for UTF-8
sudo apt update && sudo apt install locales
sudo locale-gen en_US.UTF-8
sudo update-locale LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
locale # verify settings
```

## 2.	Setup Sources:
•	Enable the Ubuntu Universe repository:

```
sudo apt install software-properties-common
sudo add-apt-repository universe
```

•	Add the ROS 2 GPG key:

```
sudo apt update && sudo apt install curl
curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```

•	Add the ROS 2 repository to your sources list:

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/ros2.list
```

## 3.	Install ROS 2 packages:
•	Update your apt repository caches:

```
sudo apt update
```

•	Upgrade your system to the latest version:

```
sudo apt upgrade
```

•	Install ROS 2 foxy desktop packages:

```
sudo apt install ros-foxy-desktop python3-argcomplete
```

## 4.	Environment Setup:
•	Source the setup script to set up your environment:

```
source /opt/ros/foxy/setup.bash
```

## 5.	Try some examples:
•	If you installed ros-foxy-desktop, you can try the following examples:
### •	C++ talker:
•	Open a terminal and source the setup file:

```
source /opt/ros/foxy/setup.bash
```

•	Run the talker node:

```
ros2 run demo_nodes_cpp talker
```

### •	Python listener:
•	Open another terminal, source the setup file, and run the listener node:

```
source /opt/ros/foxy/setup.bash
ros2 run demo_nodes_py listener
```

•	You should see the talker saying that it's publishing messages and the listener saying it heard those messages. This verifies both the C++ and Python APIs are working properly.

 ## Now we can start using ROS foxy.


