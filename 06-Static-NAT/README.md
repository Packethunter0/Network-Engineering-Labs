# Project 07: Static NAT for Public Server Access

## Objective

To configure Static NAT and allow external users to access an internal web server using a public IP address.

## Network Design

Internal Network:

* 172.16.1.0/24

Web Server:

* 172.16.1.30

Router Public Interface:

* 200.1.1.1

Public Server Address:

* 200.1.1.2

Devices:

* Router
* Switch
* Web Server
* External Client

## Key Configuration

### Configure Router Interfaces


interface g0/0

ip address 172.16.1.1 255.255.255.0

ip nat inside

interface g0/1

ip address 200.1.1.1 255.255.255.0

ip nat outside


### Configure Static NAT


ip nat inside source static 172.16.1.30 200.1.1.2


## Verification Commands

show ip nat translations
show ip nat statistics
show running-config


## Testing

From an external client:


ping 200.1.1.2






## Results

* External users successfully reached the internal web server.
* Static NAT translation was created and maintained.
* Internal server remained accessible using its private address.
* Public access was provided through a dedicated public IP address.

## Skills Demonstrated

* Static NAT Configuration
* Server Publishing
* Public and Private Address Translation
* Router Configuration
* Network Verification and Troubleshooting

## Lessons Learned

This project demonstrated how Static NAT enables external access to internal resources by creating a permanent mapping between private and public IP addresses. It also provided practical experience with server publishing and address translation verification.

