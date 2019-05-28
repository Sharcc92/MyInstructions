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


# Numpy commands
- Definie Array: `Z=np.zeros((5,2,3),np.float32)`
`F=np.array([[[1,2],[3,4],[5,6]],[[7,8],[9,10],[11,12]]])`
`Z[4][1][1]=5`
- Array characteristics: Dimensionen Z.shape
- Reshape to 2x6 Matrix instead of 2x3x2: `F_reshape = np.reshape(F, (F.shape[0], -1))`
- Mean from a picture `mean_image = np.mean(X_train, axis=0)` X is 1xD instead of NxD
- Pick certain elements from a matrix
	In [75]:1 `M=np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12]]) #NxC (2x3)
		2 `y=[1,0,1,1] #Nx1
		3 `n=X.shape[0]
		4 `M[range(n), y]
	Out[75]: `array([ 2,  4,  8, 11])`
# Pip installable Package



[Instructions](https://dzone.com/articles/executable-package-pip-install)
