# Project 07: Wireless Network Deployment and Secure Connectivity


## Objective

To deploy a secure wireless network that allows wired and wireless devices to communicate seamlessly while receiving automatic IP address assignments.

## Network Design

Network:

* 192.168.10.0/24

Main Router:

* 192.168.10.1

Wireless Router:

* 192.168.10.2

Printer 1:

* 192.168.10.10

Printer 2:

* 192.168.10.11

PCs:

* DHCP Assigned

Laptop:

* DHCP Assigned

Smartphone:

* DHCP Assigned

## Devices Used

* 1 Router
* 1 Switch
* 1 Wireless Router
* 3 PCs
* 2 Printers
* 1 Laptop
* 1 Smartphone

## Key Configuration

### Router Interface


interface g0/0

ip address 192.168.10.1 255.255.255.0

no shutdown


### DHCP Configuration


ip dhcp excluded-address 192.168.10.1 192.168.10.11

ip dhcp pool OFFICE

network 192.168.10.0 255.255.255.0

default-router 192.168.10.1

dns-server 8.8.8.8


### Wireless Router Configuration

LAN IP Address:


192.168.10.2


SSID:


OfficeWiFi


Security:


WPA2 Personal


Password:


12345678


DHCP Server:


Disabled


## Verification Commands


show ip dhcp binding


show ip dhcp pool


show running-config


## Testing

* Connect the laptop to the wireless network.
* Connect the smartphone to the wireless network.
* Verify DHCP address assignment.
* Ping the default gateway.
* Ping other wired devices on the network.

Example:


ping 192.168.10.1
ping 192.168.10.10
ping 192.168.10.11


## Results

* Wireless devices successfully connected to the network.
* DHCP automatically assigned valid IP addresses.
* Wired and wireless devices communicated successfully.
* Printers remained accessible from all devices.
* Wireless connectivity was secured using WPA2 authentication.

## Skills Demonstrated

* Wireless Network Deployment
* DHCP Configuration
* Router Configuration
* Wireless Security
* Network Connectivity Testing
* Troubleshooting Wireless Connectivity Issues

## Lessons Learned

This project provided practical experience in deploying and securing a wireless network. It reinforced the importance of DHCP, wireless security, and proper integration between wired and wireless infrastructure to ensure reliable connectivity across all devices.

