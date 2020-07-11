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
  * go to the end of the file and paste the following line. Then save and close the file.
  ```sh
   export PLUTO_DIR=/home/user/PLUTO
  ````
  
