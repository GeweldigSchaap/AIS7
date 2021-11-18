# Setting up Jetson nano for AIS7

## Installing the Linux SDK image
To install the system image to an SD card, first install [win32diskimager](https://sourceforge.net/projects/win32diskimager/)
Then, Insert the SD card in your computer (you might need a SD card reader), and open Win32DiskImager. Select the SD card in the Device
section, and open the Jetson image. Then, click write to write the image to the SD card.
(image of Win32diskimager goes here!)

*Remember that this Linux image **already has installed** two Docker containers, one for each assignment with all the needed dependencies.

## Connect over Serial connection to the Jetson from your computer
When the Jetson Nano has started up and is connected to your laptop, a new USB drive should show
up. Additionally, a serial comport is also connected. To find out which port number is assigned to the
Jetson, open the Device Manager from the Windows start menu and expand the tab “Ports (COM &
LPT)”

(image of the device manager goes here!)

Open the USB drive and launch _putty.exe_. Set the connection type to _Serial_ and Serial line to the
_comport_ (COMXX) that is assigned to the Jetson, and click _Open_.

(image of putty with the serial connection goes here!)

A Putty terminal must appear.

(image of Putty_terminal_initial goes here!)

In the Putty terminal, login with the username _jetson_, and password _jetson_.

(image of Putty_terminal_after goes here!)

*The **_jetson@nano:~$_** indicates that you are inside the Jetson, so, make sure this is the case after the previous step.

## Setup your WiFi
To setup WiFi, run the script connect_fontys_wifi or connect_home_wifi , depending on what
WiFi network you want to connect to.

For connecting to the Fontys Eduroam WiFi:

```$ sudo ./connect_fontys_wifi```

(image of Putty_eduram_connection goes Here!)

For connecting to your home WiFi (or most other WiFi networks):

```$ sudo ./connect_home_wifi```

(image of Putty_Home_connection goes Here!)


*Be aware, the **$** symbol indicates a Linux based Terminal script, **you don't need to type it**

## Connect remote desktop
So far you have stablish a connection to your Jetson to interact with it from the terminal, although useful, it is better to be able to have access to the running visual Linux base operating System as you do with your Windows Laptop (so you can use your mouse and visualize the images)

To be able to connect to the Jetson, we first need its IP address. 
This is displayed when you recently connect over the serial port in Putty. 

(image of Putty_terminal_after goes here!) 

At any time you can request/display the Jetson ip address by typing ```$ ip addr show wlan0 ```

(image of Putty_wlan0 goes here!)

Open the Jetson USB drive and launch _vncviewer_, or install a VNC client on your laptop, [like](https://www.realvnc.com/). 
Type the Jetson IP address in the VNC client running in your Laptop/PC, and connect using the password _jetson_.

(image of VNC_set_resolution goes Here!)

To fix the screen resolution to something more user friendly, open _LXTerminal_ and type:

```$ sudo ./set_screen_resolution```

##Connect to the Jupyter notebook
For Assignment 1, you will use [Jupyter notebooks](https://jupyter.org/) to follow the tutorials and to develop your assignment.

To be able to access/start the Jupyter notebook in the jetson, then, in the terminal type:

``` $ ./l4t-ml ```

(image starting_jupyter goes Here!)

Then, in your browser, go to the address that is shown on the terminal, so that would be ```http://192.168.55.1:8888``` in the image above.
Once you are in the browser Jupyter (IP address), login to the Jupyter notebook with the password _jetson_.



