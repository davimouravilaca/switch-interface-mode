sudo airmon-ng check kill
ip link set wlan0 down
ip link set wlan0 name wlan0mon

#switch to monitor mode

sudo airmon-ng check kill
sudo airmon-ng check
sudo airmon-ng start wlan0mon

#switch back to normal mode

sudo airmon-ng check kill
sudo ifconfig wlan0mon down
sudo iwconfig wlan0mon mode managed
sudo ifconfig wlan0mon up
sudo systemctl start NetworkManager
