# Pluto
## A simple guide for installation

Download the source code from [Pluto's main page](http://plutocode.ph.unito.it/download.html). You need to provide your information and click submit for the `.tar.gz` source file start downloading. The minimum prerequisites to use this code are `C Compiler`, `GNU make`, and `Python`.
Open a terminal by using `Alt+Ctrl+t` and type

```sh
sudo apt-get update
````
type your password (it will not be visible) and press `enter`. Then, to install `GNU make` and `C Compiler` enter the following command.
```sh
sudo apt-get install build-essential
````
According to our test, `Pluto` needs `python2` to work. So, Please check if you have it pre-installed by using
```sh
python2 --version
````
You will see a result similar to the follwing, if you already have it.
![python2version](https://octodex.github.com/images/yaktocat.png)

If not, you can install python2 using
```sh
sudo apt install python-minimal
````
