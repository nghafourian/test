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
python $PLUTO_DIR/setup.py
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


## Installation of pyPLUTO as a tool for PLUTO code

One of the tools you could use for`PLUTO` is `pyPLUTO`, the source code of which is included in the `PLUTO` directory that you installed in the previous section. To see the the `pyPLUTO` manual, open the PLUTO directory that you created on your own system and then go the `Doc` folder. For example, on my system I have something like `/home/neda/PLUTO/Doc`. Now open the file `pyPLUTO.html`.

Basically, you should be able to use PLUTO and pyPLUTO with both python2 or python3. However, in our experience, it only worked with python2. So, as you can see in our `Anaconda` manual, you can create a second environment *(py2)* with `python2` (version 2.7). This is easy to do following [This guide](https://docs.anaconda.com/anaconda/user-guide/tasks/switch-environment/). NOTE: *you do not need to create py3 environment*. After creating and activating `py2` environment according to the mentioned manual, install `scipy`,`numpy`, and `matplotlib` in this environment. To do so, in `ubuntu` follow these steps:

 ```sh
 make
 ````

