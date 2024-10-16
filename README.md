# rpi-eduroam
rpi setup to connect using eduroam

  
Check file:
sudo nano /etc/network/interfaces

                     
# interfaces(5) file used by ifup(8) and ifdown(8)
# Include files from /etc/network/interfaces.d:
source /etc/network/interfaces.d/*

Check file:
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf

ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
   ssid="eduroam"
   proto=RSN
   key_mgmt=WPA-EAP
   eap=PEAP
   identity="USER@DOMAIN"
   password="PASSWORD"
   phase1="peaplabel=0"
   phase2="auth=MSCHAPV2"
}
