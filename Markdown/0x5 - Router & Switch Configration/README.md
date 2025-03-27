# Network Configuration

Before configuration, you must create a topology. Here is my example topology, which is not configured before. Let's do it.

![[start.png]]

## Router Configuration

After creating a topology, the first thing you need to do is to give an IP and subnet mask to the legs of the router in the network. Then, you can do other configurations in the router CLI. However, before configuring the router, we should look at **CLI modes**.

- **User Execution Mode**: As soon as the interface-up message appears and you press enter, the router> prompt will pop up. This is called user execution mode. This mode is limited to some monitoring commands.
  
- **Privileged Mode**: As we type `enable` in user mode, we enter Privileged mode, where we can view and change the configuration of the router. Different commands like `show running-configuration`, `show IP interface brief`, etc., can run in this mode, which is used for troubleshooting purposes.

- **Global Configuration Mode**: As we type `configure terminal` in Privileged mode, we enter global configuration mode. Commands entered in this mode are called global commands, and they affect the running configuration of the router. In this mode, configurations like making a local database on the router by providing a username and password or setting enable and secret passwords can be done.

- **Interface Configuration Mode**: In this mode, only the configuration of interfaces is done. Assigning an IP address to an interface and bringing up the interface are common tasks.

| Modes                     | Access Method                              | Prompt              | Exit Method                                      |
|---------------------------|--------------------------------------------|---------------------|------------------------------------------------|
| User Execution Mode       | Login                                      | Router>             | Use `logout` command                           |
| Privilege Mode            | Use `enable` command in user mode          | Router#             | Use `disable` command to enter user mode       |
| Global Configuration Mode | Use `configure terminal` command           | Router(config)#     | Use `exit` command to enter Privilege mode     |
| Interface Mode            | Use `interface` command in global config mode | Router(config-if)# | Use `exit` or `end` to leave the mode          |

After that, let's do the configurations one by one.

## Set Clock And Time Zone

First, switch to Privileged mode, then type the `clock set` command.

![[clock.png]]

## Change Router Hostname

Switch to global configuration mode and use the `hostname` command.

![[hostname.png]]

## Give Enable Mode Password

The enable password limits the actions on the router to only certain people. Use the command `enable secret yourpassword`.

![[enable.png]]

Thereafter, when switching to Privileged mode, the router will ask for the enable password.

> While the enable password is stored as plain text in the running-config file, the enable secret is stored in a hashed state. For this reason, it is recommended to use the enable secret.

## Assign IP And Subnet Mask

To allow the router to communicate with the network and end devices, assign an IP and subnet mask to the corresponding interface.

![[ip.png]]

## Give Console Password

Generally, a console password is used when connecting the device via a console cable (rollover cable). Configure this in global configuration mode with local credentials.

![[console.png]]

## Telnet Configuration

Telnet is used for remote access to the router. In global configuration mode, first set a username and password for Telnet. Then define how many users can access the router via Telnet.

![[telnet.png]]

## SSH Configuration

SSH is also used for remote access but is more secure than Telnet. To configure SSH, first generate a crypto key using the RSA algorithm, which combines the domain name and router's hostname. Then define the RSA file size and use SSH version 2.

![[ssh.png]]

## NVRAM Configuration

To save a copy of the running configuration to startup configuration, copy it to NVRAM.

![[nvram.png]]

## Switch Configuration

### VLAN Configuration

VLANs are networks created within a local network. They isolate networks within the local network for enhanced security. This is commonly used in companies.

![[switch.png]]

### Default Gateway Configuration

Even if a switch is given an IP and subnet mask, it cannot communicate with the router unless a default gateway IP is defined.

![[defaultgateway.png]]

## Endpoint Device Configuration

After connecting an endpoint device to the network device via cable, assign an IP, subnet mask, and default gateway IP to the endpoint device.

![[pc.png]]

# Conclusion

Here is the finished example topology.

![[finish_topology.png]]
