# Set up Raspberry Pi

## Install Image on SD Card [https://www.raspberrypi.org/documentation/installation/installing-images/linux.md]

 1. Look up SD Card Mount Point

 	df -h

 1. Mount SD Card

 	df -h

  probably /dev/mmcblk0p1 (...p1 is the partition, we want the whole card without p1)

 1. Unmount SD Card

 	umount /dev/mmcblk0

 1. dd .img on SD Card

	sudo dd bs=4M if=/path/to/.img of=/dev/mmcblk0

## raspi-config

	sudo raspi-config

 ### locale [https://help.ubuntu.com/community/Locale#List_current_settings]

	list installed locales: locale -a [en_GB.UTF-8 / de_CH.UTF-8]

	list locale settings: locale

	recompile locale definition: sudo locale-gen / sudo lacale-gen en_GB.UTF-8

	change locale: update-locale LANG="en_GB.UTF-8"

	files: /etc/default/locale  //  /etc/environment

 ### set user name and password

 ### enable ssh and shell boot

## Update Upgrade Dist-Upgrade

	sudo apt-get update
	sudo apt-get dist-upgrade
	sudo apt-get upgrade


# Set up Apache [https://www.raspberrypi.org/learning/lamp-web-server-with-wordpress/worksheet/]

		sudo apt-get install apache2

		hostname -I

		http://192.168.x.y

		/var/www/html/



# Set up PHP

		sudo apt-get install php5 libapache2-mod-php5

	sudo nano /var/www/info.php
	info{
		<?php
			phpinfo();
		?>
	}.php

	http://192.168.0.200/info.php


# Set up MySQL

	sudo apt-get install mysql-server php7.0-mysql

# Set up phpMyAdmin

	

# Set up WordPress
# Set up MarkDown
# Set up Git
# Set up ...



# Configure WLAN

	sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
