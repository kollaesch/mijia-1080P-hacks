# mijia-1080P-hacks
<<<<<<< HEAD

## Goal of this project

Current hacks (see later links) for IP-Cams didn't cover the following ones. Therefor it is the goal of this project to cover Mijia 1080p and Mijia 720p.

* Mijia 1080p ([detailed Review with Pictures and comments](http://www.jayceooi.com/mijia-1080p-ip-camera-review/))
* Mijia 720p ([pictures at a possible buying source for identification](https://www.banggood.com/XIAOMI-MIJIA-360-Degree-720P-Night-Vision-Camera-Motion-Detection-Two-Way-Audio-Pan-Tilt-IR-Camera-p-1169623.html))

The findings on the way can be found in the documentation section of this repo.
(like mechanical disassembly, mainboard-pictures incl. GPIO comments, some steps of the reverse engineering)

The next open items are listed in the [todos](documentation/Todos.md).

## General information about the cams

For some systeminformation about the Mijia 1080p look at the [mijia1080p_Systeminfo](documentation/mijia1080p_Systeminfo.md)


--- 


=======

## Hardware 

### mijia 1080p
* Mainboard: ![Mainboard with RX TX](../master/images/mijia_1080p/mainboard_rx_tx.jpg) thanks @ferdydek
* CPU: GM8136S http://www.grain-media.com/html/8136S_8135S.htm

### mijia 720p 360°
* Mainboard frontside: ![Mainboard with RX TX](../master/images/mijia_720p_360/Frontside_with_Sensor_and_IO_pins.jpg)
* Mainboard backside: ![Mainboard with RX TX](../master/images/mijia_720p_360/Backside_with_SoC.jpg) 
* CPU: GM8135S http://www.grain-media.com/html/8136S_8135S.htm

## Software
* SDK: "GM8136 SDK release v1.0.rar" http://pan.baidu.com/share/link?uk=2553453276&shareid=3324610145
* UART-Boot-Log: https://pastebin.com/raw/nt4GUAeF thanks @kollaesch