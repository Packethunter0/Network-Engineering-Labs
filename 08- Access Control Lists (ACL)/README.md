# Project 06: Access Control Lists (ACL)


## Objective

To enhance network security by controlling access to resources using ACLs.

## Network Design

Departments:

* HR
* Finance
* IT

Networks:

* 192.168.10.0/24
* 192.168.20.0/24
* 192.168.30.0/24

Devices:

* Router
* Switches
* Multiple PCs

## Key Configuration

### Block Finance Internet Access

access-list 1 deny 192.168.20.0 0.0.0.255

access-list 1 permit any


### Apply ACL

interface g0/1

ip access-group 1 out


## Verification Commands


show access-lists

show running-config


## Testing

* Verify HR can access external networks.
* Verify IT can access external networks.
* Verify Finance cannot access external networks.
* Verify internal communication remains functional.

## Results

* Security policies were successfully enforced.
* Unauthorized traffic was blocked.
* Internal communication continued to function normally.

## Skills Demonstrated

* ACL Configuration
* Traffic Filtering
* Security Policy Enforcement
* Access Management
* Troubleshooting

## Lessons Learned

This project demonstrated how ACLs can be used to enforce network security policies and control user access to resources.

