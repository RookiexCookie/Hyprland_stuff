# Using Android as Second Monitor

To make android act as a second monitor in hyprland first we have to download some softwares in arch and in andoroid
for linux install wayvnc
and for android avnc or anyother trusted vnc app
and make sure both devices are connected to same network

Now time for the main thing
Write these in Terminal

First to create virtual second monitor and by default resolutuion will be1920x1080@60<br>
`hyprctl output create headless`<br>

next we will get the virtual monitor actual name, it will be like HEADLESS-2 etc<br>
`hyprctl monitors`<br>

after getting the name if you want to change the resolution or offset you can change with this<br>
`hyprctl keyword monitor HEADLESS-2,1340x800@60,-1366x0,1`<br>


this makes the res lower and -1366 makes my left monitor
and lastly to get the android working as a second screen you would find your local ip with `ip a`
then using wayvnc you will stream it <br>
`wayvnc --output=HEADLESS-2   -f 45 192.168.xx.xxx 5900 &`<br>


after this is done you will punch in the ip and the port in your android vnc app and 
now your phone screen will be showing the second monitor
