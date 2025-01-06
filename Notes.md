

# Marlin config 


## related projects and links 

https://linuxcnc.org/ LinuxCNC controls CNC machines. It can drive milling machines, lathes, 3D printers, laser cutters, plasma cutters, robot arms, hexapods, and more.




# Octoprint config
set the rpi4 local address as 
SSH key 


Webcam feed 
 in Classic Webcam plugin 
 Stream URL http://192.168.0.3/webcam/?action=stream


# Klipper firmware amd 


https://github.com/dw-0/kiauh Klipper Installation And Update Helper
```sh
sudo apt-get update && sudo apt-get install git -y

cd ~ && git clone https://github.com/dw-0/kiauh.git 


```
used https://www.youtube.com/watch?v=N41JY1Gukuk for guidance 


calcul de la position de la probe du bltouch avec les moteurs 
probre sur le (0,0) avec x 41 y 7.00

nozzle sur le (0,0) avec x  -1 et y 3.0 ===>> probe offsets -40,-4

bltouch: z_offset: 3.290
apres correction du zero 
bltouch: z_offset: 4.200

# Raspberry Pi 

had to reset the wifi in 
sudo raspi-config
1 and 1

didn't seem to work
finally managed to get the new firmware out and on the ender and this seems to have improved stability of the system. Still not really reassured this won't come back to bite me in the worst posible moment. 


# moonraker.conf

[update_manager timelapse]
type: git_repo
primary_branch: main
path: ~/moonraker-timelapse
origin: https://github.com/mainsail-crew/moonraker-timelapse.git
managed_services: klipper moonraker