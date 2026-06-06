# Project 02: Inter-VLAN Routing Using Router-on-a-Stick


## Objective

To enable communication between VLAN 100, VLAN 200, and VLAN 300 using a single router interface.

## Network Design

VLAN 100:

* Network: 192.168.10.0/24
* Gateway: 192.168.10.1

VLAN 200:

* Network: 192.168.20.0/24
* Gateway: 192.168.20.1

VLAN 300:

* Network: 192.168.30.0/24
* Gateway: 192.168.30.1

## Key Configuration

### Switch Trunk Port


interface fa0/21

switchport mode trunk


### Router Configuration


interface g0/0
no shutdown

interface g0/0.100

encapsulation dot1Q 100

ip address 192.168.10.1 255.255.255.0

interface g0/0.200

encapsulation dot1Q 200

ip address 192.168.20.1 255.255.255.0

interface g0/0.300

encapsulation dot1Q 300

ip address 192.168.30.1 255.255.255.0

## Verification Commands


show ip interface brief

show running-config

show interfaces trunk


## Testing


ping 192.168.20.2

ping 192.168.30.2


## Results

* Students successfully communicated with Teachers.
* Students successfully communicated with Management.
* Teachers successfully communicated with Management.
* Inter-VLAN communication was verified using ICMP ping tests.

## Skills Demonstrated

* Router-on-a-Stick
* 802.1Q Encapsulation
* Subinterface Configuration
* Inter-VLAN Routing
* Gateway Configuration

## Lessons Learned

This project demonstrated how a single router interface can support multiple VLANs and provide communication between departments through subinterfaces and VLAN tagging.

