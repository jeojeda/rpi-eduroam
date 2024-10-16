# rpi-eduroam
rpi setup to connect using eduroam
``````
  
Check file:
`sudo nano /etc/network/interfaces
`
                    
`# interfaces(5) file used by ifup(8) and ifdown(8)`
`# Include files from /etc/network/interfaces.d:`
`source /etc/network/interfaces.d/*`


Check file:
``sudo nano /etc/wpa_supplicant/wpa_supplicant.conf

`ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev`
`update_config=1`


`network={`
`ssid="eduroam"`
`proto=RSN`
`key_mgmt=WPA-EAP`
`eap=PEAP`
`identity="USER@DOMAIN"`
`password="PASSWORD"`
`phase1="peaplabel=0"`
`phase2="auth=MSCHAPV2"`
`}`

---


---


`Check file:`
`/etc/dhcpcd. conf`

`interface wlan0`
`env ifwireless=1`
`env wpa_supplicant_driver=wext,nl80211`




original file
  GNU nano 5.4                    /etc/dhcpcd.conf                              

# Most distributions have NTP support.
#option ntp_servers

# A ServerID is required by RFC2131.
require dhcp_server_identifier

# Generate SLAAC address using the Hardware Address of the interface
#slaac hwaddr
# OR generate Stable Private IPv6 Addresses based from the DUID
slaac private

# Example static IP configuration:
#interface eth0
#static ip_address=192.168.0.10/24
#static ip6_address=fd51:42f8:caae:d92e::ff/64
#static routers=192.168.0.1
#static domain_name_servers=192.168.0.1 8.8.8.8 fd51:42f8:caae:d92e::1

# It is possible to fall back to a static IP if DHCP fails:
# define static profile
#profile static_eth0
#static ip_address=192.168.1.23/24
#static routers=192.168.1.1
#static domain_name_servers=192.168.1.1

# fallback to static profile on eth0
#interface eth0
#fallback static_eth0

# interface wlan0
# static ip_address=192.168.0.3
# static routers=192.1.68.0.1
# static domain_name_servers=8.8.8.8
# SSID WAAM

#new lines
interface wlan0
env ifwireless=1
env wpa_supplicant_driver=wext,nl80211
#end new lines



