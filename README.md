# RGB Xmas Tree running on balena

## Required hardware

* Raspberry Pi (tested with Zero W, Pi 2 model B, Pi 4 model B)
* [3D RGB Xmas Tree for Raspberry Pi](https://thepihut.com/products/3d-rgb-xmas-tree-for-raspberry-pi)
* 8GB SD Card or similar (Sandisk Extreme Pro recommended)
* Power supply

## Setup and configuration

<img width="624" alt="xmas-rgb-tree-pihut-balena" src="https://user-images.githubusercontent.com/173156/209328704-5167655f-67ac-41cf-bb6f-b80cc59f72f5.png">

Get the Xmas tree PCB and solder the 2 lateral pieces (it works as well if you connect straightforward the PCB). Once soldered it should look like this image below.

<img width="569" alt="rgb-xmas-tree-balena-raspberrypi" src="https://user-images.githubusercontent.com/173156/209328758-277f7712-e613-475b-aa18-8b439e79c66f.png">

Once mounted, running this project is as simple as deploying it to a balenaCloud application. You can do it in just one click by using the button below:

[![deploy button](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/balena-rgbxmastree&defaultDeviceType=raspberry-pi)

## Customization
With the environment variables below you can customize your 3D RGB Xmas Tree.

Variable Name | Value | Description | Default
------------ | ------------- | ------------- | -------------
**`BRIGHTNESS`** | `NUMBER` | You can change the brightness of the led's with the `BRIGHTNESS` variable; set it anywhere from `1` to `100`. You'll find that 100 is _extremely bright_ and even 8 (default) is bright enough if the tree is on your desk :)| 8
**`DELAY`** | `NUMBER` | You can change the delay between updates of led's with the `DELAY` variable (seconds); set it anywhere from `0` to `~`. | 0.5
**`STARTTIME`** | `NUMBER` | Set start time with 24 hours format from 0000 to 2359 | 0000
**`STOPTIME`** | `NUMBER` | Set stop time with 24 hours format from 0000 to 2359 | 2359


### Philips Hue integration
Wouldn't it be nice if the xmas tree goes on and off at the same time as the lights in the room it's standing. If you are using Philips Hue lights and the tree is able to reach the Hue bridge you can connect it so the tree will go on when a specific light is turned on.
To turn this feature on set `USE_HUE_LIGHT_STATUS` to True and configure the following params:

`USE_HUE_LIGHT_STATUS` True

`HUE_IP` Set the IP address of the Hue bridge

`HUE_USERNAME` Set the username for the Hue bridge see following link to get a username https://developers.meethue.com/develop/get-started-2/

`HUE_LIGHT_NAME` Set the name of the Hue light you want to sync with the xmas tree

`HUE_USE_SSL` Set to True if you want to use HTTPS else it will be HTTP

