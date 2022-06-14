# Yiimp Install Scrypt (update 2022-06-12)
***********************************************
<a href="https://discord.gg/GVZ4tchkKc"><img src="https://img.shields.io/discord/904564600354254898.svg?style=flat&label=Discord %3C3%20&color=7289DA%22" alt="Join Community Badge"/></a>





###

## Install script for yiimp on Ubuntu Server 16.04 / 18.04

Use this script on fresh install ubuntu Server 16.04 / 18.04. ``` No other version is currently supported. ``` This install script will get you 95% ready to go with yiimp. There are a few things you need to do after the main install is finished.

## First of all you need to create a new user i use pool.
```
adduser pool
```
When you can create your user you need to add the new user to sudo group.
```
adduser pool sudo

```
### Now do a quick reboot and log back in to your pool user.

Now when you have created your new user and added it to sudo group and reboot and log back in you are ready to start the installation.

```
sudo su pool
```
### clone the git repo.
```
git clone https://github.com/afiniel/yiimp_install_script.git
```
### cd to the installer map.
```
cd yiimp_install_script
```
### Now it's time to start the installation.
```
bash install.sh
```
- > It will take some time for the installation to be finnished and it will do for you.

***********************************

## This script has an interactive beginning and will ask for the following information :

- Server Name (You can enter )(Example)): example.com or your ip of your vps like this 80.41.52.63)
- Are you using a subdomain (subdomain.example.com)
- Enter support email
- Set stratum to AutoExchange
- Your Public IP for admin access (Put your PERSONNAL IP, NOT IP of your VPS)
- Install Fail2ban
- Install UFW and configure ports
- Install LetsEncrypt SSL

***********************************

Finish! Remember to 
```
sudo reboot
```
when the installer tell you to.

- Access your new pool at (No-SSL) example.com/site/      (With SSL) https://www.example.com/site/
- Access AdminPanel: (No-SSL) example.com/site/AdminPanel (With SSL) https://www.example.com/site/AdminPanel


### Update keys.php if you have exchange (Enable)

- > Update your public keys for exchanges (If Enable). update with Your own keys.. , you can change it by nano to,
```
sudo nano /etc/yiimp/keys.php
```
### Change AdminRights

- > **If you want change your AdminRights to something else :** Edit this file "/SiteController.php" and Line 11 => change 'AdminPanel'

```
sudo nano /var/web/yaamp/modules/site/SiteController.php
```
###### :bangbang: **IMPORTANT** : 

- The configuration of yiimp and coin require a minimum of knowledge in linux
- Your mysql information (login/Password) is saved in **~/.my.cnf**

*****************************************************************************

While I did add some server security to the script, it is every server owners responsibility to fully secure their own servers. After the installation you will still need to customize your serverconfig.php file to your liking, add your API keys, and build/add your coins to the control panel. 
