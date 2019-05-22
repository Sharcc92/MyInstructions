# MyInstructions
- Install Python 3.6 	(http://ubuntuhandbook.org/index.php/2017/07/install-python-3-6-1-in-ubuntu-16-04-lts/)
	`sudo add-apt-repository ppa:jonathonf/python-3.6`
	`sudo apt-get update`
	`sudo apt-get install python3.6`
	Afterwards point to python3.6 according to instruction

- Install Pip3
	`sudo apt-get update`
	`sudo apt-get -y install python3-pip`
	Check Version: `pip3 -V`

- VirtualEnvironment: `pip3 install virtualenv`, Init Project: `virtualenv -p python3 PROJECTNAME`, Check Version: `virtualenv --version`


# Non related commands
- List of ROS Services `ros2 service list`
- Switch between windows `byobu` (Start with `byobu`. Use F2 to switch and F3 to create more parallel terminals)
- Storage Space of Ubuntu system: `df -h`
- Reduce storage space by showing list of biggest programms: `du -sh *`

# Pip installable Package



[Instructions](https://dzone.com/articles/executable-package-pip-install)
