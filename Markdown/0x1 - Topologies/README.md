## Types of Computer Networks

### **PAN**: **Personal Area Network**

A PAN connects electronic devices within a user's immediate area. The range of a PAN typically spans a few centimeters to a few meters. A common example is the **Bluetooth connection** between an earpiece and a smartphone. Other devices, such as laptops, tablets, and printers, can also be connected within a PAN.

- **Real-world application**: Connecting Bluetooth headphones to a phone or pairing a smartwatch to a smartphone.
### **WLAN**: **Wireless Local Area Network**

A WLAN consists of devices connected using **radio transmissions** rather than wired connections, such as Wi-Fi. Anyone connected to Wi-Fi is using a WLAN.

- **Real-world application**: Home Wi-Fi network or public Wi-Fi in cafes and airports.
### **LAN**: **Local Area Network**

A LAN links devices within a **single physical location**, like a **home, office, or building**. It can vary in size from a simple home network to a larger network within a business or educational institution.

- **Real-world application**: Office or school network where all computers, printers, and other devices are connected to a central router or switch.
### **MAN**: **Metropolitan Area Network**

A MAN covers a **larger area than a LAN but is smaller than a WAN**, typically connecting multiple computers within the same city or across nearby cities. It's designed for customers requiring **high-speed connectivity**, like an Internet Service Provider (ISP).

- **Real-world application**: An ISP providing high-speed Internet to an entire city or government buildings connected across a metropolitan area.
### **WAN**: **Wide Area Network**

A WAN connects **multiple LANs or other networks**, often spanning **vast geographical areas**. The **Internet** is the largest example of a WAN, interconnecting various global networks.

- **Real-world application**: The global Internet, connecting millions of devices across the world.

---
![[types_of_computer_networks.png]]
### Physical Topologies

Physical topology refers to the physical layout of the network, including the arrangement of devices and cables. It affects cost, bandwidth capacity, and the ease of installation.

#### Types of Physical Topologies:

- **Bus Topology**
- **Ring Topology**
- **Star Topology**
- **Mesh Topology**
- **Tree Topology**

---
## Bus Topology

![[bus_topology.png]]
In bus topology, **all devices are connected to a single central cable** (called the bus or backbone). This setup is simple but can become problematic if the main cable fails, affecting the entire network.

- **Real-world application**: Older networks or small home networks where simplicity is prioritized over reliability.

|             **Advantage**              |                    **Problem**                     |
| :------------------------------------: | :------------------------------------------------: |
|        Easy to add new devices.        |           Difficult to detect problems.            |
| A broken device doesn’t affect others. | A failure in the main network impacts all devices. |

---

## Ring Topology

![[ring_topology.png]]
Ring topology connects devices in a circular fashion, where each device has two neighboring devices to communicate with. **Repeaters** are used to prevent data loss, especially in large networks.

- **Real-world application**: Token Ring networks used in legacy systems.

|**Advantage**|**Problem**|
|:-:|:-:|
|Device count doesn’t affect performance.|A problem with any device affects the entire network.|

---

## Star Topology

![[star_topology.png]]
In star topology, devices are **connected to a central hub** via cables. The hub acts as the central node, and if it fails, the entire network goes down.

- **Real-world application**: Most modern home and office networks, where devices are connected to a central Wi-Fi router or switch.

|             **Advantage**             |                **Problem**                |
| :-----------------------------------: | :---------------------------------------: |
|       Easy to add new devices.        |         Requires a lot of cables.         |
| Problem detection is straightforward. | Hub failure brings down the whole system. |

---

## Mesh Topology

![[mesh_topology.png]]
In mesh topology, each device is connected to every other device, creating multiple paths for data to travel.

- **Real-world application**: High-availability networks, such as those used by data centers, where reliable communication and redundancy are crucial.

|**Advantage**|**Problem**|
|:-:|:-:|
|Fast communication between nodes.|Expensive due to high cable requirements.|
|Reliable data transfer through dedicated channels.|Maintenance is costly.|
|Provides high security and privacy.|Installation and configuration are complex.|

---

## Tree Topology

![[tree-topology.png]]
Tree topology combines characteristics of star and bus topologies, creating a structure that resembles a tree. There is a central node (trunk) with other nodes branching off.

- **Real-world application**: Large enterprise networks, like those used by universities or large businesses with multiple departments.

|**Advantage**|**Problem**|
|:-:|:-:|
|Easy error detection and correction.|System failure if the central hub fails.|
|Allows easy addition of new devices.|High cabling costs.|
|Enables network isolation and prioritization.|Reconfiguration can be difficult when adding devices.|

---
