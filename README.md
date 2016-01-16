# Browser Streaming Bot

This is my own customised version of the browser streaming bot scripts that
come with a GoPiGo which is in turn based on various other people's hard work.

I have just hacked it about to suit my own nefarious purposes.

The original README is still available at
[README.original.md](README.original.md) which contains links to the folks who
should be credited with the heavy lifting.

## Setup

Clone the repository on to the PI

```
https://github.com/adamphillips/pi-browser-streaming
cd pi-browser-streaming
```

Ensure that the web server script is executable

```
chmod +x robot_web_server.py
```

Run the script (currently needs sudo)

```
sudo ./robot_web_server.py
```

Visit the control page in a browser. This runs on port 98 and the host is the
name of your Raspberry PI. By default, Raspbian for Robots uses a host name of
dex. So on your controlling computer or phone visit

```
http://dex:98
```

More info on setting up is available at [the Dexter Industries project
page](http://www.dexterindustries.com/GoPiGo/projects/python-examples-for-the-raspberry-pi/raspberry-pi-browser-streaming-robot/)

## Important note about the camera

Due to wiring constraints I have mounted my camera upside down on the chassis.
Therefore in order for the bot to be usable, I have rotated the image by 180
degrees and inverted the left and right controls.

[This is the
commit](https://github.com/adamphillips/pi-browser-streaming/commit/88b56e9da7b5b627a6c1180feef233fadad25b03)
where I inverted the robot controls. The image rotation is performed in the
`#camera` section of www/layout.css . Look for the vendor specific
`-transform:rotate(180deg)` entries (there are 3) and remove them if you want
to put it back.
