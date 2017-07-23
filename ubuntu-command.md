## Reconfigure Display Manager
```
sudo dpkg-reconfigure lightdm
```

## Install KDE Plasma
```
sudo add-apt-repository ppa:kubuntu-ppa/backports
sudo apt-get update && sudo apt-get dist-upgrade
sudo apt-get install kubuntu-desktop
```

## Install GNOME
```
sudo apt-get update
sudo apt-get install gdm3
```

## RhythmBox fix 
```
sudo apt-get install ubuntu-restricted-extras
```

## Software Installation
```
sudo dpkg -i <file.deb>
```

## Dependecies fix
```
sudo apt-get install -f
```

## Update and Upgrade packages
```
sudo apt-get update
sudo apt-get upgrade
```

## Install Tweak Tools
```
sudo apt-get install unity-tweak-tool
sudo apt-get install gnome-tweak-tool
```

## Disable ipv6 completely
```
sudo nano /etc/sysctl.conf
```
### Copy and paste the following 3 lines at the bottom of the file
```
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
net.ipv6.conf.lo.disable_ipv6 = 1
```
### Save It and Run The following command
```
sudo sysctl -p
```

## Update Boot Logo
```
sudo update-alternatives --config default.plymouth
sudo update-initramfs -u
```

## Find Which App or Process using a specific port
```
sudo netstat -tanpl|grep <port>`
```

## Start Xampp
```
sudo service mysql stop
sudo service apache2 stop
sudo /opt/lampp/manager-linux-x64.run
```

## Install firefox developer edition
```
sudo add-apt-repository ppa:ubuntu-mozilla-daily/firefox-aurora
sudo apt update
sudo apt install firefox
```

## Enable rc.local
```
sudo systemctl enable rc-local.service
reboot
```

## Install NextCloud Client
```
sudo add-apt-repository ppa:nextcloud-devs/client
sudo apt-get update
sudo apt-get install nextcloud-client
```

### [MaxySpark](http://maxyspark.com)