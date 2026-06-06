# VLAN Segmentation Using Cisco Packet Tracer

## Objective

To create separate broadcast domains for different departments while maintaining communication between users belonging to the same department across multiple switches.

## Topology

Switch0
Switch1
Switch2

VLAN 100 - Students
VLAN 200 - Teachers
VLAN 300 - Management

## Configuration

### Create VLANs

enable
conf t

vlan 100
name STUDENTS

vlan 200
name TEACHERS

vlan 300
name MANAGEMENT

vlan 99
name Native
### Configure Trunks

interface g0/1
switchport mode trunk

## Verification

show vlan brief

show interfaces trunk

## Results

Students communicated successfully across all switches.

Teachers communicated successfully across all switches.

Management communicated successfully across all switches.

Inter-VLAN communication was blocked as expected.
