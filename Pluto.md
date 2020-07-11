# Pluto
## A simple guide for installation on GNU/Linux OS

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

If not, you can install python2 using
```sh
sudo apt install python-minimal
````
Now that you have the basic prerequisites for the `Pluto` code installed, you may proceed to installation of the code. See the  [documentiation file](http://plutocode.ph.unito.it/userguide.pdf) for more details. In the following, we will see the installation method explained on page 6 of the user-guide.  

Copy the file `pluto-4.3.tar.gz` that you previously downloaded to your home folder. Then open a terminal and follow these steps:
* unzip the file:
```sh
tar xvf pluto-4.3.tar.gz
````
* Export the Pluto directory path:
  * open the `.bashrc` file using `gedit` (or e.g. `vim`)
   ```sh
   sudo gedit ~/.bashrc 
   ````
  * go to the end of the file and paste the following line and replace `/home/user/PLUTO` with the address of the `pluto` directory on your own system. _(you may check the directory address by opening a terminal window in that directory and run the command `pwd` in the terminal.)_ Then save and close the file.
   ```sh
    export PLUTO_DIR=/home/user/PLUTO
   ````
  * now type the follwing command in the terminal and press `Enter`.
   ```sh
    . ~/.bashrc
   ````
   ```sh
    source ~/.bashrc
   ````
The `pluto` directory is now known for your system. So, you can continue to use the code. Check this example to make sure it works.

Change directory (`cd`) to the example's directory and follow
```sh
cd $PLUTO_DIR/Test_Problems/HD/Sod
````
```sh
cp definitions_01.h definitions.h
````
```sh
cp pluto_01.ini pluto.ini
````
Run the `python` script
```sh
python $PLUTO_DIR/setup.py
````
  
