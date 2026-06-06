# Project 04: Dynamic Host Configuration Protocol (DHCP)


## Objective

To automate IP address assignment and reduce manual network configuration using DHCP.

## Network Design

Network:

* 192.168.1.0/24

Gateway:

* 192.168.1.1

Reserved Addresses:

* 192.168.1.1 to 192.168.1.10

DHCP Range:

* 192.168.1.11 to 192.168.1.254

Devices:

* 1 Router
* 1 Switch
* 4 PCs

## Key Configuration

### Configure Router Interface


interface g0/0

ip address 192.168.1.1 255.255.255.0

no shutdown


### Exclude Reserved Addresses


ip dhcp excluded-address 192.168.1.1 192.168.1.10


### Configure DHCP Pool


ip dhcp pool LAN

network 192.168.1.0 255.255.255.0

default-router 192.168.1.1

dns-server 8.8.8.8


## Verification Commands


show ip dhcp binding

show ip dhcp pool

show running-config


## Testing

* Set all PCs to DHCP mode.
* Verify automatic IP assignment.
* Ping the router gateway.

## Results

* All PCs received IP addresses automatically.
* Reserved addresses were not assigned.
* End-to-end connectivity was verified.

## Skills Demonstrated

* DHCP Configuration
* IP Address Management
* Router Services
* Network Automation
* Troubleshooting

## Lessons Learned

This project demonstrated how DHCP simplifies network administration and reduces configuration errors by automatically assigning network settings to clients.

