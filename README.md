# Smartphone-Doorlock
Doorlock that can be locked or unlocked through your smartphone

You’ll want to make sure you have [node.js](https://nodejs.org/en/) installed on your Raspberry Pi. Adafruit has a nice guide on their [website](https://learn.adafruit.com/node-embedded-development/installing-node-dot-js).

## Installation
If running on Jessie Lite, install pigpio:

```
sudo apt-get install pigpio
```

Navigate to the folder you want to clone the repository and type

```
git clone https://github.com/HackerHouseYT/Smartphone-Doorlock.git
```

Once done cloning, navigate into the folder.

```
cd Smartphone-Doorlock
```

Install the dependencies (if it fails, delete node_modules and retry without sudo)

```
sudo npm install
```

Add the Blynk auth token by setting the `BLYNK_TOKEN` enviroment variable.

```
export BLYNK_TOKEN=Your Token Here
```

`sudo node doorlock.js`

## Running at Startup

To run at startup, you can add the start command to your `rc.local`.

Type `pwd` to get your current directory. I highlighted this and copied it with `control-c`.

Edit the `rc.local` file with vim.

```
sudo vim /etc/rc.local
```

Press `i`, then scroll down and add `sudo node <Your Directory From pwd>/doorlock.js`

Press `esc`, then type `:wq!` to save and exit. Restart the Pi to start the program.

