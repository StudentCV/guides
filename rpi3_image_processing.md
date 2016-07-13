# From Zero to Image

This guide will get you all set up for Python-based image processing on your Raspberry Pi 3! You can also use this guide with other hardware if you apply some slight tweaks (e.g. pick another architecture when downloading software). You should also be familiar with basic usage of your system's terminal. Let's get started!

## Prerequisites
1. This guide assumes that you're running Debian Jessie or a similar derivate (think Ubuntu) on your machine
2. Ensure your system's software is up-to-date by running the following commands from your terminal:
	* `sudo apt-get update`
	* `sudo apt-get dist-upgrade`
	* `sudo raspi-update`

## pylon
Pylon contains all the software we need for interacting with Basler cameras. Builds are provided for multiple platforms.

1. Download the latest pylon version from [here](http://www.baslerweb.com/de/support/download-uebersicht/downloads-software?type=28&series=0&model=0), pick the hardfloat ARM version for linux
2. Unpack the file to a directory of choice
3. Follow the instructions in the `INSTALL` file. Do not attempt to run the pylon viewer as it is not bundled with ARM releases
4. After successful installation plug in e.g. your Basler USB camera
5. Now we will check if everything works. In your terminal move to pylon's `Samples/Grab` directory and execute `make`, then run `./Grab`, you should see some text scrolling with information about pictures being grabbed

## OpenCV and Python 3
In this step we'll set up Python 3 and the OpenCV image processing library. Just follow the instructions over [here](http://www.pyimagesearch.com/2016/04/18/install-guide-raspberry-pi-3-raspbian-jessie-opencv-3/). Remember to follow the instructions for Python 3 and not 2.7!

## PyPylon
The only missing part is connecting Python to your camera now. PyPylon takes care of this task.

1. First, ensure you're using the `cv` virtualenv you created while installing OpenCV
2. Get your exact python version by running `python --version` from within your virtualenv
3. Using this information, pick the corresponding PyPylon version from here **LINK MISSING** (e.g. Python 3.4 → `..cp34-cp34m-linux_armv7l.whl`)
4. Install the `whl` file with pip via `pip install *path-to-whl*`
5. Open a Python REPL with `python` and check that running `import pypylon.pylon` does not yield any errors

Done! You can either try out our example projects now or create some cool stuff of your own. Have fun!
