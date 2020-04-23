# OctoPrint-PortLister

Through my own experimentation, I've come to the conclusion that this plugin, for
whatever reason ignores the values placed in config.yaml and always has a 20 second
delay. In this fork, I have hard coded a 0 second delay time so it initiates the connect
sequence almost instantly. I'm successfully using this connected to Creality3D Version 1.1.3
mainboards that are running Marlin 2.0.X Bugfix that take approximately 5-6 seconds to finish 
booting to the status screen, also taking into account the fact that initiating the USB connection
causes the mainboard to restart its boot sequence. This fork was made to run in combonation
with [@UnchartedBull's OctoDash](https://github.com/UnchartedBull/OctoDash) and OctoPrint-PSUControl
available in Octoprint's built in plugin repo, to switch a relay to power up the mainboard.

Have you noticed that if you load up the OctoPrint web page when your printer is
off, the printer's port isn't in the list?  Then when you turn on the printer
you have to refresh the page to make it show up?  This plugin fixes that.

It watches for the device to appear (when you turn it on) and then notifies all
the web clients to refresh the list of ports.

It also (if you have autoconnect turned on), will automatically connect to the
printer (if the new port is the same as the one you've selected in connection
settings) after a reasonable (long) delay to wait for the printer to actually
come on.  ~~The default delay is 20 secs.  It's settable in config.yaml~~, if
anybody uses this plugin besides me, I could be talked into a settings page.

## Setup

Install via the Octoprint plugin manager by copying/pasting the below URL
into the "... from URL" field and click install

    https://github.com/mikekscholz/OctoPrint-PortLister/archive/master.zip

**OR,**

Download the zip file via the "Clone or Download" button and then use the 
plugin managers "browse" button to find where you saved the download on your
computer.
(personally I like keeping local copies of obscure forks so I dont have to hunt them down all the time)


## Configuration

~~In .octoprint/config.yaml, the autoconnect_delay can be configured to
something other than the default 20 seconds it takes my printer to boot up.~~
```
plugins:
  portlister:
    autoconnect_delay: 20
```
