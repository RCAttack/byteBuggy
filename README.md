# Raspberry Pi software set-up and WiFi dongle drivers install


This wright up is to get you started on setting up the raspberry pi with an OS and the drivers installed.
For this project we used Kali OS on the raspberry pi.

HARDWARE REQUIREMENTS
--------------

Raspberry Pi (a pi 3 and above is recommended will discuss later on)

RC car chassis or your preferred method of transporting the pi

External WiFi dongle (you will need a dongle that can be in monitor mode and send injection packets) here is a [link](https://deviwiki.com/wiki/List_of_Wireless_Adapters_That_Support_Monitor_Mode_and_Packet_Injection) to find out what WiFi dongles can perform such tasks.
The dongle we used for this project is [BrosTrend](https://www.amazon.com/BrosTrend-1200Mbps-Adapter-Wireless-Antennas/dp/B01IEU7UZ0/ref=sr_1_4?crid=2WD555C8HO8JW&dib=eyJ2IjoiMSJ9.1RoOXZhpDLoXglp84TKBjMLZp32RpUamYpqU2VyewkskX6mXvPThqx0m4pL0htVhNbWWFNdMGxBoK8JHjfI6ttLL4SKViS-8g81BMIlQj32yRy16E2kbQfMUDM5XTSi-ntL8PlwaEuCtOEBiMDPE3MhnkTJERtLQ-8JDu-IoeSOQNNvmQfHea_0xEW_ONEXQXQVpaQf39AO717a2q2gm3z0YK0CGOO6xZsCJaH_B_Bc.wwgo9_5NtiZUto06pyx-BAbdnaAS6XhLhGhmX5AJVb8&dib_tag=se&keywords=brostrend+wifi+adapter&qid=1708889102&sprefix=brostrend+%2Caps%2C133&sr=8-4)

Power bank (anything that is relatively smart that can have multiple out-puts)
We are using the [ANKER](https://www.amazon.com/Delivery-PowerCore-Nintendo-Official-13400mAh-Portable/dp/B07DMFL3SJ/ref=cm_cr_arp_d_pb_opt?ie=UTF8&th=1) This power bank is discontinued in Amazon but something similar is fine.

SOFTWARE REQUIREMENTS
--------------------

Raspberry Kali OS

Aircrack-ng

Drivers for the WiFi dongle (The drivers will be listed in the instructions manual when you receive the device). If you are unable to see them, usually google the name of the device with driver install will help guide on getting the driver.


THE STEPS INCLUDE
======

**RASPBERRY PI IMAGER:**

* The simplest way to install the OS is to download the. [raspberry pi imager](https://www.raspberrypi.com/software/)
Once installed and the window is open you should see something like this. ![image](https://github.com/RCAttack/byteBuggy/assets/112519100/9aa846d8-c07d-47d3-a5bf-89a296224906)
* Insert a blank SD card into your computer above 8Gb.

**CHOOSE YOUR DEVICE:**

* Choose a device you are using. We went with the Raspberry pi 4 4Gb ram, But a raspberry pi 3 or above will work.
You should see this on your page when clicked on CHOOSE DEVICE. ![image](https://github.com/RCAttack/byteBuggy/assets/112519100/1e6e04ef-b168-4836-887d-430eb786092a)

**CHOOSING THE OPERATING SYSTEM:**

* Choose your operating system. Navigate to CHOOSE OS. ![image](https://github.com/RCAttack/byteBuggy/assets/112519100/26d22924-b172-42a6-a754-782a8f5fbf5d)
* Scroll down to other specific purpose OS ![image](https://github.com/RCAttack/byteBuggy/assets/112519100/3c997ce7-94ef-4161-bab0-b820a1f2e134)
* Then on the Kali image we went with the 64bit version as it will handle more data, the reason why we recommend a pi 3 or above. ![image](https://github.com/RCAttack/byteBuggy/assets/112519100/30ac7a3b-3fd1-4470-bfb2-6a0b629c4764)

**YOUR STORAGE:**

* Lastly the SD card you inserted after installing the raspberry pi imager should show up when you click on CHOOSE STORAGE.
* Let it flash the image onto your SD card. Once finished it will prompt you that it has completed flashing and you may remove your SD card.
* install the SD card to your pi and provide power with an HDMI out-put.

The Amazon links are not affiliates. We recive no proceeds.

KALI OS SET-UP
======

On first boot you should see the kernel loading then restarting. Then the Kali OS will appear like so type `kali` for the username and `kali` for the password.

![image](https://github.com/RCAttack/byteBuggy/assets/112519100/2d1b0c67-efcb-402f-b6a7-b7778f0249d0)

You now have access to the Kali OS!

![image](https://github.com/RCAttack/byteBuggy/assets/112519100/e9ca1b01-e710-47fa-b79d-13e35768872f)

**CONNECTING TO A WIFI NETWORK:**

on the top right screen you will see a network icon click it and this window will pop up.
![image](https://github.com/RCAttack/byteBuggy/assets/112519100/391f4ffe-e075-47a8-854e-473fb8e4ce55)

and click on available networks and type in your WiFi credentials.

**UPDATING KALI:**

Ensuring your newly Kali OS is updated so no new downloaded files have missing dependencies.
  navigate to the command line on the top left corner next to firefox (black box).
 
```
sudo apt update
```
when the update is completed reboot.

```
reboot
```

**CHANGING PASSWORD:**

It is highly recommended that you change your password.

```
sudo passwd
```

Enter the password you would like to use ( you won't be able to see your password as you type it, but it will ask you to retype it).


**ENSURING YOU HAVE SSH ENABLED:**

To install ssh in kali.

```
sudo apt install ssh
```

  * Enabling ssh
    
	```
	sudo raspi-config
	```
  * Navigate to interface options
  * ssh
  * yes
  * Exit
  * then reboot


**DOWNLOADING YOUR WIFI DRIVER:**

* As stated above the manufacturer should have instructions on downloading the drivers.
* if it is not clear then google the `name` of the WiFi dongle with `linux driver install` in the search bar.
* our driver is [link](https://linux.brostrend.com/)


**ip ADDRESS:**

```
ifconfig
```

![image](https://github.com/RCAttack/byteBuggy/assets/112519100/597c4ce7-3ecc-4db8-a49c-849181c5848c)

you will need to save the `inet` number in order to ssh into your pi.

























