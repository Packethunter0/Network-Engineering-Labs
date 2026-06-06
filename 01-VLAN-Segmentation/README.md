# Project 01: VLAN Segmentation Across Multiple Switches


## Objective

To create separate broadcast domains for Students, Teachers, and Management and verify communication within the same VLAN across multiple switches.

## Topology

* Switch0
* Switch1
* Switch2

VLAN Assignment:

* VLAN 100: Students
* VLAN 200: Teachers
* VLAN 300: Management

## IP Addressing

Students:

* 192.168.10.2
* 192.168.10.3
* 192.168.10.4

Teachers:

* 192.168.20.2
* 192.168.20.3
* 192.168.20.4

Management:

* 192.168.30.2
* 192.168.30.3
* 192.168.30.4

## Key Configuration

### Create VLANs


vlan 100
name STUDENTS

vlan 200
name TEACHERS

vlan 300
name MANAGEMENT


### Assign Access Ports







interface fa0/1

switchport mode access

switchport access vlan 100







interface fa0/2

switchport mode access

switchport access vlan 200







interface fa0/3

switchport mode access

switchport access vlan 300



### Configure Trunk Links



interface g0/1

switchport mode trunk


interface g0/2

switchport mode trunk


## Verification Commands


show vlan brief

show interfaces trunk

show mac address-table

## Results
* Students communicated successfully across all switches.
* Teachers communicated successfully across all switches.
* Management communicated successfully across all switches.
* Communication between different VLANs was blocked.

## Skills Demonstrated

* VLAN Configuration
* Access Port Assignment
* Trunk Configuration
* Layer 2 Switching
* Network Troubleshooting

## Lessons Learned

This project demonstrated how VLANs reduce broadcast traffic and logically separate departments while allowing devices within the same VLAN to communicate across multiple switches.
