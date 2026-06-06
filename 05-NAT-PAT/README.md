# Project 05: Network Address Translation (NAT) and Port Address Translation (PAT)


## Objective

To provide internet access for internal users using private addressing and address translation techniques.

## Network Design

LAN:

* 192.168.1.0/24

Router LAN Interface:

* 192.168.1.1

Public Interface:

* 200.1.1.1

Devices:

* Router
* Switch
* Three PCs

## Key Configuration

### Configure Interfaces


interface g0/0

ip address 192.168.1.1 255.255.255.0

ip nat inside

interface g0/1

ip address 200.1.1.1 255.255.255.0

ip nat outside


### Configure PAT


access-list 1 permit 192.168.1.0 0.0.0.255

ip nat inside source list 1 interface g0/1 overload

## Verification Commands


show ip nat translations

show ip nat statistics

show access-lists


## Testing

* Ping external networks from internal hosts.
* Verify NAT translation entries.
* Confirm multiple devices share one public IP.

## Results

* Internal users successfully accessed external resources.
* Address translation occurred correctly.
* Public IP conservation was achieved.

## Skills Demonstrated

* NAT Configuration
* PAT Configuration
* Access Lists
* Public and Private Addressing
* Internet Connectivity

## Lessons Learned

This project demonstrated how NAT and PAT allow organizations to efficiently utilize public IP addresses while maintaining internal private addressing schemes.

