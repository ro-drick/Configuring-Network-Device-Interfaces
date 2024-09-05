# Cisco Packet Tracer - Network Interface Configuration Practice

This repository contains configurations for a Cisco Packet Tracer exercise where I configured various network devices such as routers, switches, and PCs. The following tasks were completed as part of the practice exercise:
<img src="https://github.com/ro-drick/Configuring-interfaces/blob/main/configuring-interfaces.PNG">

## Table of Contents
- [Overview](#Overview)
- [Devices](#devices)
- [Practice Tasks](#practice-tasks)
- [Task 1: Configure Hostnames](#task-1-configure-hostnames)
- [Task 2: Configure IP Addresses](#task-2-configure-ip-addresses)
- [Task 3: Configure Speed and Duplex Settings](#task-3-configure-speed-and-duplex-settings)
- [Task 4: Configure Interface Descriptions](#task-4-configure-interface-descriptions)
- [Task 5: Disable Unused Interfaces](#task-5-disable-unused-interfaces)
---

## Overview

This exercise focuses on configuring network devices in Cisco Packet Tracer. The main objectives include setting hostnames, assigning IP addresses, configuring speed and duplex settings, adding interface descriptions, and disabling unused interfaces.

## Devices

The network topology consists of the following devices:
- **R1**: Cisco Router
- **SW1**: Cisco Switch
- **SW2**: Cisco Switch
- **PC1**: End Device (Personal Computer)
- **PC2**: End Device (Personal Computer)
- **PC3**: End Device (Personal Computer)
- **PC4**: End Device (Personal Computer)

---

## Practice Tasks

### Task 1: Configure Hostnames

For each network device, configure a unique hostname for easy identification in the network. The following hostnames were set:

- **R1**: `R1`
- **SW1**: `SW1`
- **SW2**: `SW2`

#### Example Configuration:
```plaintext
# On R1
Router(config)# hostname R1

# On SW1
Switch(config)# hostname SW1

# On SW2
Switch(config)# hostname SW2
```
### Task 2: Configure IP Addresses

Assign appropriate IP addresses to each of the devices (R1, PC1, PC2, PC3, PC4). Below is the IP address scheme used:

- **R1**: `172.16.255.254/16` on GigabitEthernet0/0
- **PC1**: `172.16.0.1/16`
- **PC2**: `172.16.0.2/16`
- **PC3**: `172.16.0.3/16`
- **PC4**: `172.16.0.4/16`

#### Example Configuration:
```plaintext
# On R1 (GigabitEthernet0/0 interface)
R1(config)# interface GigabitEthernet0/0
R1(config-if)# ip address 172.16.255.254 255.255.0.0
R1(config-if)# no shutdown

# On each PC
# PC1 (Static IP)
PC1 IP address: 172.16.0.1
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.1.1

# Similar steps for PC2, PC3, and PC4 with their respective IPs
```
### Task 3: Configure Speed and Duplex Settings

Manually configure the speed and duplex settings on interfaces connected to other networking devices (R1, SW1, SW2). This ensures optimal performance for inter-device communication.

#### Example Configuration:
```plaintext
# On R1 (GigabitEthernet0/1 interface to SW1)
R1(config)# interface GigabitEthernet0/1
R1(config-if)# speed 1000
R1(config-if)# duplex full

# On SW1 (FastEthernet0/1 interface to SW2)
SW1(config)# interface FastEthernet0/1
SW1(config-if)# speed 100
SW1(config-if)# duplex full
```
### Task 4: Configure Interface Descriptions

Add descriptions to interfaces to clearly indicate their function or connected devices. This improves network management and troubleshooting.

#### Example Configuration:
```plaintext
# On R1 (GigabitEthernet0/0 interface to PC1)
R1(config)# interface GigabitEthernet0/0
R1(config-if)# description ## to SW1 ##

# On SW1 (FastEthernet0/1 interface to SW2)
SW1(config)# interface FastEthernet0/1
SW1(config-if)# description ## to end host ##
```
### Task 5: Disable Unused Interfaces

To improve network security and reduce unnecessary traffic, disable interfaces that are not connected to any other devices.

#### Example Configuration:
```plaintext
# On SW1 (Disable unused FastEthernet ports)
SW1(config)# interface range FastEthernet0/2 - 24
SW1(config-if-range)# shutdown

# On R1 (Disable unused GigabitEthernet interfaces)
R1(config)# interface GigabitEthernet0/2
R1(config-if)# shutdown
```
## Acknowledgements


Special thanks to **Jeremy's IT Lab** for providing valuable resources and tutorials that greatly contributed to the completion of this exercise. His in-depth explanations and practical demonstrations have been instrumental in enhancing my understanding of Cisco networking concepts and the effective use of Packet Tracer.

For more information and additional resources, visit [Jeremy's IT Lab](https://jeremysitlab.com/) and check out his YouTube for the full course, [Jeremy's IT Lab Free CCNA 200-301 | Complete Course](https://www.youtube.com/playlist?list=PLxbwE86jKRgMpuZuLBivzlM8s2Dk5lXBQ)
