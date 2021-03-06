# MyInstructions
# Ubuntu commands
- Check ubuntu version: ` lsb_release -a`
- Check Python version: `python -V` or `python3 -V`
- Install Python 3.6 	(http://ubuntuhandbook.org/index.php/2017/07/install-python-3-6-1-in-ubuntu-16-04-lts/)
	`sudo add-apt-repository ppa:jonathonf/python-3.6`
	`sudo apt-get update`
	`sudo apt-get install python3.6`
	Afterwards point to python3.6 according to instruction

- Install Pip3
	`sudo apt-get update`
	`sudo apt-get -y install python3-pip`
	Check Version: `pip3 -V`
- Install VirtualEnvironment: `pip3 install virtualenv`, Init Project: `virtualenv -p python3 PROJECTNAME`, Check Version: `virtualenv --version`
- Install Anaconda: (https://www.digitalocean.com/community/tutorials/how-to-install-anaconda-on-ubuntu-18-04-quickstart)
	Test installation: `conda list`
	Create new env: `conda create --name NEW_ENV python=3`
	Activate new env: `conda activate NEW_ENV` (e.g. anomaly1)
	Deactivate env: `conda deactivatecon`
	Install Pytorch in Conda: `conda install -c pytorch pytorch`
- Mount Windows drive in Ubuntu shell: `cd /mnt/c/DL/i2dl
- See hidden folders `ls -a`
# Pytorch
- Tutorial: (https://pytorch.org/tutorials/beginner/deep_learning_60min_blitz.html)
- Function: kwargs: 
	in function header (* collects all the positional arg in a tuple, ** collects all the keyword args in a dict) 
	e.g. `functionA(*a,**kw):`, `functionA(1, 2, a=1, b=2)` results in a=(1,2),kw={'a': 1,'b':2}
	in a function call (* unpacks a list or tuple into position args, ** unpacks a dictionary into keyword args)
	e.g. lis=[1, 2], dic={'a': 10, 'b':20}, `functionA(*lis, **dic):` results in (1, 2) as args and {'a': 10, 'b': 20}
- Matlplotlib+Glob: get files from directory 
	`images=glob.glob('../generated/*.jpg')`, `for i, image in enumerate(images,1):`, `image = Image.open(image)`,`plt.subplot(1,len(images),i)`, `plt.test(0.5,0.5,str((2,3,i)),fontsize=18,ha='center')`,`plt.show()`
- Arrays: Expand tensor: `tensor=tensor.expand(1,2,3)` or tensors with dimension `torch.ones_like(TENSOR)` or `torch.zeros_like(TENSOR)`
# Github
- check branch: `git status`
- pull from git repo: `git pull`
- change brach `git checkout`
- add file `git add $filename` then `git commit -m "$message"` then `git push origin $branchname` (e.g. master). The name origin stands for 'on your system' and the possible options can be seen mit the command `git remote -v`
- share folder between linux embedded in windows: "cd /mnt/c/$shared folder name$"
- delete local changes: `git checkout .` - Removes Unstaged Tracked files ONLY [Type 2]
`git clean -f` - Removes Unstaged UnTracked files ONLY [Type 3]
`git reset --hard` - Removes Staged Tracked and UnStaged Tracked files ONLY[Type 1, Type 2]
`git stash -u` - Removes all changes [Type 1, Type 2, Type 3]
# Classes
- Definition: `class LinearClassifier(object):
    `"""Description."""
    'def __init__(self):
        'self.W = None
    def train(self, Para):
- Inherent: `class SoftmaxClassifier(LinearClassifier): 
		`def fct(self, para):
        		`return 0
- Instance: e.g. `softmax = SoftmaxClassifier()`
- Import class from same folder: `from .linear_classifier import LinearClassifier

# Functions:
- lambda: `relu = lambda val: np.maximum(0, val)`
- print sorted list: `results={}` `lr, reg =0.3 , 0.2` `results[(lr, reg)] = (0.5, 0.6)` `lr, reg =0.1 , 0.4` `results[(lr, reg)] = (0.7, 0.8)` `print(results)` `for (lr, reg) in sorted(results): 
`train_accuracy, val_accuracy = results[(lr, reg)]
 print('lr %e reg %e train accuracy: %f val accuracy: %f' % (lr, reg, train_accuracy, val_accuracy))`
 - list: `as=np.arange(1e-1, 10e-1,1e-1)` with `for a in as:` or alternative `steps_lr = 3#20` `lr = [1e-3, 1e-4]` `for i in np.linspace(lr[0], lr[1], steps_lr):`
 - get indices and values from a list (with startvalue from indices with 1) `Z=[100, 100]`, `for i, v in enumerate(Z, 1):` `print("l: ",l)` `print("d:",d)`
 - define a dictionary: `word_to_ind = dict(), for i in range(len(array)): word_to_ind[array[i]] = i`
- make a config file Make a config file with default values: in main `config = {'a': 1e-3, 'b': v}`, `next_w, _ = sgd_momentum(w, dw, config=config)` and in function `def sgd_momentum(w, dw, config=None):` , `if config is None: config = {}`, `config.setdefault('a', 1e-2) `,`config.setdefault('momentum', 0.9) `, `mue = config['momentum']`

# Non related commands
- List of ROS Services `ros2 service list`
- timestamp: `tic = time.time()`
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
- Array indexing: https://docs.scipy.org/doc/numpy-1.10.0/user/basics.indexing.html
- mean of array: np.mean(y_train == y_train_pred)
- Range: array=np.arange(1e-7, 5e-7,1e-7)

# Pip installable Package

# Unsorted
Example fct with kwargs:
self.update_rule = kwargs.pop('update_rule', 'sgd')

What does // and % mean?
num_batches = N // batch_size % is division with abrunden
        if N % batch_size != 0: %(mod fuction)

Makes y_pred = np.hstack(y_pred) to 0,1?

What is batch normalization, dropout?

Why makes it deterministic? seed: If not None, then pass this random seed to the dropout layers. This
          will make the dropout layers deteriminstic so we can gradient check the
          model.
Inititialze from a std distr.:  np.random.randn(input_dim, hidden_dim)
Get indices and values from a matrix: for l, d in enumerate(hidden_dims, 1):


another option for a for loop for l in range(1, self.num_layers) or for i in range(self.num_layers - 1, 0, -1):
Save sth in a list e.g. outputs of a function from a for loop: caches = [] before for-loop: caches.append(x) and get the last items with c=temp.pop()


[Instructions](https://dzone.com/articles/executable-package-pip-install)
