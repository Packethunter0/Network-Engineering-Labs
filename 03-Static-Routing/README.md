# Project 03: Static Routing Between Two Networks


## Objective

To establish communication between two remote LANs using static routing.

## Network Design

LAN A:

* Network: 192.168.1.0/24
* Gateway: 192.168.1.1

LAN B:

* Network: 192.168.2.0/24
* Gateway: 192.168.2.1

WAN Link:

* Network: 209.165.200.8/30

Router0:

* WAN IP: 209.165.200.9

Router1:

* WAN IP: 209.165.200.10

## Key Configuration

### Router0


interface g0/0

ip address 192.168.1.1 255.255.255.0

interface g0/1

ip address 209.165.200.9 255.255.255.252


ip route 192.168.2.0 255.255.255.0 209.165.200.10


### Router1


interface g0/0

ip address 192.168.2.1 255.255.255.0

interface g0/1

ip address 209.165.200.10 255.255.255.252

ip route 192.168.1.0 255.255.255.0 209.165.200.9


## Verification Commands



show ip route

show ip interface brief


## Testing

From LAN A:


ping 192.168.2.2


From LAN B:


ping 192.168.1.2


## Results

* Devices in LAN A successfully communicated with devices in LAN B.
* Static routes appeared correctly in the routing table.
* End-to-end connectivity was verified.

## Skills Demonstrated

* Static Routing
* Routing Table Analysis
* WAN Configuration
* Router-to-Router Communication
* Network Troubleshooting

## Lessons Learned

This project demonstrated how routers forward traffic between remote networks using manually configured routes and highlighted the importance of next-hop addressing.

