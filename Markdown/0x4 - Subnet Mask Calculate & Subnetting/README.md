# Subnet Mask Calculation

An IP address is a 32-bit number that uniquely identifies a single device on an IP network. These 32 bits are divided into **network bits** and **host bits**, determined by the subnet mask. IP addresses are typically written in the **dotted decimal format**, where each 8-bit section (octet) is converted from binary to decimal for readability. For example, the binary IP `10101100.00010000.11111110.00000001` is written as `172.16.254.1`.

### Subnet Mask and Network Segmentation

The subnet mask divides the IP address into the **network portion** and the **host portion**:

- **Network Portion**: Identifies the subnet the device belongs to.
- **Host Portion**: Identifies the specific device within the subnet.

The **CIDR notation** (e.g., `/24`) indicates the number of 1s in the subnet mask. For example, `/24` corresponds to a subnet mask of `255.255.255.0`.

### Example: `192.168.63.8/24`

1. **Network Address**: The network address represents the first address in the range. For `/24`, the last 8 bits are host bits (`0s`), so the network address is `192.168.63.0`.
2. **Broadcast Address**: The broadcast address is the last address in the range. For `/24`, the host bits are all `1s`, so the broadcast address is `192.168.63.255`.
3. **Host Bits and Subnet Mask**:
    - Host bits = `32 - 24 = 8`.
    - Subnet Mask = `255.255.255.0` (derived by converting `24 network bits` to binary).

---

**IP Addressing Examples**

|**Example IP**|**Host Bits**|**Network Address**|**Broadcast Address**|**Subnet Mask**|
|---|---|---|---|---|
|144.128.16.9/24|8|144.128.16.0|144.128.16.255|255.255.255.0|
|172.127.46.10/22|10|172.127.44.0|172.127.47.255|255.255.252.0|
|192.168.36.7/26|6|192.168.36.0|192.168.36.63|255.255.255.192|
|27.129.10.2/30|2|27.129.10.0|27.129.10.3|255.255.255.252|
|56.81.33.17/16|16|56.81.0.0|56.81.255.255|255.255.0.0|
|14.34.64.4/23|9|14.34.64.0|14.34.65.255|255.255.254.0|
|20.20.20.20/13|19|20.16.0.0|20.23.255.255|255.248.0.0|
|39.70.2.1/18|14|39.70.0.0|39.70.63.255|255.255.192.0|
|100.100.100.100/8|24|100.0.0.0|100.255.255.255|255.0.0.0|
|205.21.53.13/3|29|192.0.0.0|223.255.255.255|224.0.0.0|
|114.182.47.31/9|23|114.128.0.0|114.255.255.255|255.128.0.0|

---

This version corrects inaccuracies, improves readability, and maintains the integrity of the technical explanations. Let me know if you’d like further adjustments.

![[ip_addressing.png]]

![[subnetmask-calculate.png]]


Here some more examples table about ip addressing.

|Example IP|Host Bit|Network Adress|Broadcast Address|Subnet Mask|
|:---:|:---:|:---:|:---:|:---:|
|144.128.16.9/24|8|144.128.16.0|144.128.16.255|255.255.255.0|
|172.127.46.10/22|10|172.127.44.0|172.127.47.255|255.255.252.0|
|192.168.36.7/26|6|192.168.36.0|192.168.36.63|255.255.255.192|
|27.129.10.2/30|2|27.129.10.0|27.129.10.3|255.255.255.252|
|56.81.33.17/16|16|56.81.0.0|56.81.255.255|255.255.0.0|
|14.34.64.4/23|9|14.34.64.0|14.34.65.255 | 255.255.254.0|
|20.20.20.20/13|19|20.16.0.0|20.23.255.255 | 255.248.0.0|
|39.70.2.1/18|14|39.70.0.0 |39.70.63.255  | 255.255.192.0|
|100.100.100.100/8|24|100.0.0.0|100.255.255.255 |255.0.0.0|
|205.21.53.13/3|29|192.0.0.0|223.255.255.255 |224.0.0.0|
|114.182.47.31/9|23|114.128.0.0|114.255.255.255  |255.128.0.0|


# Subnetting

The process of dividing a network into 2/more networks is called subnetting. A subnet, or subnetwork, is a network **inside a network**. **Subnets make networks more efficient**. Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination. Also, we can **always create 2^n subnets in a network**. For example if we wanted to dividing 192.168.10.0/24 network into 3 subnetworks, we wouldn't. Instead, we can dividing 192.168.10.0/24 network into 4 subnetworks and use three of them. Time to understand how subnetting works.

## How Divide Subnetting?

Subnetting works are smiliar to ip addressing process. Again, we convert the IP address into binary format to find the subnet mask and network address. However, there is an important point which means our network ID is current network ID + intended numbers of subnet. Please, keep an eye out! 

Afterwards, we draw a perpendicular line to divide it into the subnet immediately after the network ID. It is where the magic happens. After the last dot, we need to increment like 1,10,11,100,101,110 the remainder starting from 0. Let's look at example pictures for better understanding.

![[subnet.png]]

![[subnetting.png]]

If we take the example in the picture as reference, we have **4 subnets**. There are : 

|Subnet|Network Address| Broadcast Address|Avaliable IP Range|
|:-:|:-:|:-:|:-:|
|A|192.168.10.0|192.168.10.63|192.168.10.1-62|
|B|192.168.10.64|192.168.10.127|192.168.10.65-126|
|C|192.168.10.128|192.168.10.191|192.168.10.129-190|
|D|192.168.10.192|192.168.10.255|192.168.10.193-254|


---

# **Subnetting with Serial Connection**

A **Serial Connection** is commonly used to establish a WAN (Wide Area Network) connection, typically provided by a service provider through a leased line. These dedicated leased lines are often purchased by organizations to interconnect offices or business sites that are geographically distant, sometimes spanning thousands of miles. The cost of leased lines depends on the **bandwidth** offered by the service provider.

---

## **Leased Line and Serial Connection in Cisco Networks**

In Cisco-based networks, a **Serial Connection** is often used for leased line setups. The default encapsulation protocol for Cisco routers is **HDLC** (High-Level Data Link Control). While HDLC works seamlessly between Cisco devices, it is a Cisco proprietary protocol, meaning it **does not interoperate with non-Cisco routers**.

To establish a connection between Cisco and non-Cisco routers, both devices must be configured to use a common **data link protocol**, such as **PPP (Point-to-Point Protocol)**. A mismatch in protocols will result in a failed connection, and the interface will display a status of **down**.

### **Protocol Considerations**:

- **New Cisco Routers**: By default, use HDLC for serial interfaces.
- **Older Cisco Routers or Mixed Vendors**: Always check the data link protocol configuration. If there is a protocol mismatch, configure both routers to use the same protocol (e.g., PPP).

---

## **Configuring a Serial Connection Example**

To demonstrate, let’s configure a serial connection between two routers. In this setup:

- A **clock rate** of **56,000** is configured on the **DCE (Data Communications Equipment)** side to provide a speed of **56 Kbps**.
- In real-world scenarios, the clock speed is managed by the service provider, based on the bandwidth of the leased line.

Here, we simulate the service provider using a serial cable. The router on the **DCE side** is configured with the clock speed.

---

### **Configuration Steps**:

1. **Check the Cable Type**: Use the `show controllers serial 0/0/0` command to determine if the interface is DCE or DTE.
    
    - If it is **DCE**, you must configure the clock rate.
2. **Set the Clock Rate on DCE**:
    
    ```bash
    Router(config)# interface serial 0/0/0
    Router(config-if)# clock rate 56000
    ```
    
3. **Set the Data Link Protocol**:
    
    - For HDLC (default):
        
        ```bash
        Router(config-if)# encapsulation hdlc
        ```
        
    - For PPP (to ensure compatibility):
        
        ```bash
        Router(config-if)# encapsulation ppp
        ```
        
4. **Enable the Interface**:
    
    ```bash
    Router(config-if)# no shutdown
    ```
    
5. **Verify the Configuration**: Use the following commands to check the status:
    
    ```bash
    Router# show ip interface brief
    Router# show running-config
    ```
    

---

### **Key Takeaways**:

- The **DCE side** always requires the clock rate to be configured.
- **Protocol compatibility** is crucial for successful communication.
- Use **PPP** if working with routers from different vendors.

This example illustrates the fundamental setup for a serial connection, often encountered in Cisco networking environments. 

---

## **Default Configuration**

The first step in the setup is subnetting the network in the topology and assigning IP addresses correctly. In this example, the **192.168.10.0/24** network is divided into **4 subnetworks**. After subnetting, the routers and switches were configured, and four routers were connected using serial cables. If you are unfamiliar with configuring routers and switches, refer to the [guide here](https://github.com/wasny0ps/Network-Notes/tree/main/0x5%20-%20Router%20%26%20Switch%20Configration).

### **Required Hardware**

To use a serial connection:

- You must have a **serial cable** and a **NIM-2T module** installed on the router.
- Before starting, power off the router and insert the **NIM-2T module** into the physical port as shown below:
![[serial.png]]
Once the module is installed, connect the serial cable to the serial port of the router. After configuring the physical connections, the topology looks like this:

![[subnetted--topology.png]]

---

## **Serial Interface Configuration**

Now, configure the serial interfaces of the routers:

1. Assign IP addresses and subnet masks for each router using the CLI.
2. Set up a **clock rate** of **56,000** for `Router 0`, `Router 1`, and `Router 2`.
3. Use **static routing** to establish communication between the routers. If you are unfamiliar with static routing, learn more from [this guide](https://github.com/wasny0ps/Network-Notes/tree/main/0x7%20-%20Static%20%26%20Default%20Routing).

Due to the amount of configuration required, all necessary commands have been saved in a configuration file for convenience. You can access the commands [here](https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/configration.txt).

---

### **Finalized Topology**

After completing the configurations, the finished topology looks like this:

![[end_topology.png]]

You can also download the complete example file [here](https://github.com/wasny0ps/Network-Notes/blob/main/0x4%20-%20Subnet%20Mask%20Calculate%20%26%20Subnetting/source/subnetting_with_serial_connection_routing_with_default.pkt).

---

Let me know if you need additional edits, diagrams, or further explanations!

