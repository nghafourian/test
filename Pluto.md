# Pluto
## A simple guide for installation on GNU/Linux OS (ubuntu based distros)

Download the source code from [Pluto's main page](http://plutocode.ph.unito.it/download.html). You need to provide your information and click submit for the `.tar.gz` source file start downloading. The minimum prerequisites to use this code are `C Compiler`, `GNU make`, and `Python`.
Open a terminal by using `Alt+Ctrl+t` and type

```sh
sudo apt-get update
````
type your password (it will not be visible) and press `Enter`. Then, to install `GNU make` and `C Compiler` enter the following command.
```sh
sudo apt-get install build-essential
````
According to our tests, `Pluto` needs `python2` to work. So, please check if you have it pre-installed by using
```sh
python2 --version
````
You will see a result similar to the follwing, if you already have it.
![python2version](https://github.com/Shenavar/pics/blob/master/python.jpg)

_note that everything before the `$` sign shows the user and directory address that I am working in, and what you see after `$` is the code. The `~` sign is a representative of the `home directory`_

If `python2` is not installed on your system, you can install it using
```sh
sudo apt-get install python-minimal
````

Before continuing to the installation of `pluto`, install `gnuplot`. We will need it later to plot our results. In your terminal window type 
```sh
sudo apt-get install gnuplot
````
provide your password if needed. After the installation you can enter the `gnuplot` envirnoment by simply typing `gnuplot` in the terminal. You can exit by typing `q` and pressing `Enter`.

Now that you have the basic prerequisites for the `Pluto` code installed, you may proceed to the installation of the code. See the documentiation file ([user-guide](http://plutocode.ph.unito.it/userguide.pdf)) for more details. In the following, we will see the installation method explained on page 6 of the user-guide.  

Copy the file `pluto-4.3.tar.gz` that you previously downloaded to your home folder. Then open a terminal and follow these steps:
* unzip the file:
```sh
tar zxvf pluto-4.3.tar.gz
````
* Export the Pluto directory path:
  * open the `.bashrc` file using `gedit` (or e.g. `vim`). _if you do not have `gedit` installed, install it by command `sudo apt-get install gedit`and continue_
   ```sh
   sudo gedit ~/.bashrc 
   ````
  * go to the end of the file and paste the following line and replace `/home/user/PLUTO` with the address of the `pluto` directory on your own system. _(you may check the directory address by opening a terminal window in that directory and run the command `pwd` in the terminal.)_ Then save and close the file.
   ```sh
    export PLUTO_DIR=/home/user/PLUTO
   ````
  * now type one of the follwing commands in the terminal and press `Enter`.
   ```sh
    source ~/.bashrc
   ````
   or   
   
   ```sh
    . ~/.bashrc
   ````
   
The `pluto` directory is now known for your system. So, you can continue to use the code. Check this example to make sure it works.

* Change directory (`cd`) to the example's directory and follow the next commands
```sh
cd $PLUTO_DIR/Test_Problems/HD/Sod
````
```sh
cp definitions_01.h definitions.h
````
```sh
cp pluto_01.ini pluto.ini
````
* Run the `python` script
```sh
python2 $PLUTO_DIR/setup.py
````
 and select “Setup problem” from the main menu, see Fig. 1.2 of [documentiation file](http://plutocode.ph.unito.it/userguide.pdf). You can choose (by pressing Enter) or modify the default setting using the arrow keys.  
* Continue pressing `Enter` and choosing your desired setup options. Once you return to the main menu, select `Change makefile`, choose a suitable makefile (for this basic installation in Linux choose `Linux.gcc.defs` option) and press enter.
* Exit from the main menu (“Quit” or press ’q’) and type the following to compile the code. make
 ```sh
 make
 ````
* Make sure you are in the `$PLUTO_DIR/Test_Problems/HD/Sod` directory. You can now run the code by typing
 ```sh
 ./pluto
 ````
  At this point, PLUTO reads the initialization file pluto.ini and starts integrating. The run should take a few seconds (or less) and the integration log should be dumped to screen.
* you can now plot the results using `gnuplot`.  Type `gnuplot` in the terminal and enter its environment. Then type
```sh
 plot "data.0001.dbl" bin array=400:400:400 form="%double" ind 0
````
You should now see the results if everything is working fine.



# Installation of pyPLUTO as a tool for PLUTO code

*Here we assume you have already installed `Anaconda3` using the 
[Anaconda manual](https://github.com/Shenavar/Anaconda-Installation.md/blob/master/Anaconda%20Installation.md).*


### py2 environment and the requirements for pyPLUTO
Basically, you should be able to use `PLUTO` and `pyPLUTO` with any of the `python` versions (python2 or python3). However, in our experience, it only works with python2. So, you can create a second environment *(py2)* with `python2` (version 2.7). This is easy to do following [This guide](https://docs.anaconda.com/anaconda/user-guide/tasks/switch-environment/). 

NOTE 1: You still need the free internet (e.g. you can use lantern if you are in Iran) as mentioned in the above manual.

NOTE 2: You do not need to create py3 environment. 

In `Ubuntu/Mint` you can use the following command in the terminal.:
```sh
conda create --name py2 python=2.7
````
to activate `py2` in Linux:
```sh
conda activate py2
````
NOTE 1: It might ask you to initialize `conda`. In this case, type `conda init` in terminal and `Enter`. Then activate `py2`.

NOTE 2: you can later deactivate `py2` environment by typing `conda deactivate` in the terminal.

After creating and activating `py2` environment in your terminal, you need to install `scipy`,`numpy`, and `matplotlib` in this environment (`py2`). To do so, you can follow [this guide](https://phoenixnap.com/kb/install-numpy) , or in `Ubuntu/MInt` follow these steps:
* Activate py2 environment:
 ```sh
 conda activate py2
 ````
 * Check your python version. you should see a version of 2.7 python in this environment. 
 ```sh
 python --version
 ````
![plotplot](https://github.com/Shenavar/pics/blob/master/3n.png) 
* install `pip` for python2:
 ```sh
 sudo apt install python-pip
 ````
 * Use `pip` to install SciPy, NumPy and matplotlib:
 ```sh
 pip install scipy
````
```sh
pip install numpy
````
```sh
pip install matplotlib
````
Now we are ready to install `pyPLUTO`. 

### pyPLUTO installation:

One of the tools you could use for`PLUTO` is `pyPLUTO`, the source code of which is included in the `PLUTO` directory that you installed in the previous section. To see the the `pyPLUTO` manual, open the PLUTO directory that you created on your own system and then go the `Doc` folder. For example, on my system I have something like `/home/neda/PLUTO/Doc`. Now open the file `pyPLUTO.html`and go to **GETTING STARTED --> Installation** and follow the second (recommended) method as we state here:
* Create a directory to store the pyPLUTO modules. For example I create this directory on my home directory.
```sh
cd \home\neda
```
```sh
mkdir MyPython_Modules
````
* Go back to the pyPLUTO directory:
```sh
 cd $PLUTO_DIR/Tools/pyPLUTO
```
* Install the code in the directory created : 
```sh
python setup.py install --prefix=<path to MyPython_Modules>
````
e.g. in my case I will have `python setup.py install --prefix=\home\neda\MyPython_Modules`.

* Then append the following in your .bashrc:
 open the file with command `gedit ~/.bashrc`. Go to the end of the file and add the following two lines 
```sh
export PYTHONPATH =<path to MyPython_Modules>/lib/python<ver>/site-packages
````
where <ver> is the python version which the user have used to install the package. e.g. in my case I want to work with python2.7 and I will write `export PYTHONPATH="/home/neda/MyPython_Modules/lib/python2.7/site-packages"` and also
```sh
export PATH =<path to MyPython_Modules>/bin:$PATH
````
e.g. in my case `export PATH="/home/neda/MyPython_Modules/bin:$PATH"`. After adding these two lines save the file and close it.

* type the following in your terminal and press `Enter`:
```sh
source ~\.bashrc
````
Your installation must be done. Now let's check it by running an example from the manual (`$PLUTO_DIR/Tools/pyPLUTO/doc/example.html#sod`). We will plot the results of the previous test of the `PLUTO` code (Sod example). 

* open a terminal and activate `py2` environment:
```sh
conda activate py
````
* open python:
```sh
python
````
* Type the following commands:
```python
import os
import sys
from numpy import *
from matplotlib.pyplot import *
import pyPLUTO as pp

plutodir = os.environ['PLUTO_DIR']
wdir = plutodir+'/Test_Problems/HD/Sod/'
nlinf = pp.nlast_info(w_dir=wdir)

D = pp.pload(nlinf['nlast'],w_dir=wdir) # Loading the data into a pload object D.

f1 = figure()
ax1 = f1.add_subplot(111)
plot(D.x1,D.rho,'r',D.x1,D.prs,'k',D.x1,D.vx1,'g')
xlabel(r'x')
ylabel(r'$\rho$ [red], P [black], $V_{\rm x}$ [green]')
title(r'Sod shock Tube test')
axis([0.0,1.0,-0.2,1.2])
savefig('sod_1.pdf')
show()
````
You will see something like this:

![py2-python-import](https://github.com/Shenavar/pics/blob/master/1n.png)

![plotcode](https://github.com/Shenavar/pics/blob/master/2n.png)

![plotplot](https://github.com/Shenavar/pics/blob/master/3n.png)




