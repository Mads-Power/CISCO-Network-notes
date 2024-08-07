# HOST to HOST

## Network characteristics

- topology
- Speed
- cost
- Security
- Availability
- Scalability
- Reliability

## The OSI Reference Model owerview

Upper layers:

---

- 7 application
- 6 presentation
- 5 session

Lower Layers = network engineers

---

- 4 Transport = TCP/UDS,port
- 3 Network = IP, Devices: Routers
- 2 Data-Link = Ethernet MAC Address, Devices: switches
- 1 Physical

## OSI Acronyms

The classic: Please Do Not Throw Sausage Pizza Away

## TCP/IP stack

- Application: Data
- Transport: Segment
- Internet: Packet
- Network Access: Frame

### The lower OSI LAyers

- 4 Transport layer =

  - if TCP or UDP is being used and the port number.
  - The transport Layer defines services to segment, transfer, and reassemble the data for infidividual communications between devices.
  - It Breaks Down large files into smaller segments that are less likely to incur transmission problems.

- layer 3 Network =

  - the most important information at the network layer is the source and destination IP address
  - router operate at layer 3
  - The network layer provides connectivity and path selection between two host systems that may be located on geographically separated networks.
  - the network layer is the layer that manages the connectivity of hosts by providing logical addressing.

- layer 2 The Data-Link Layer
  - The most important information at the data-link layer is the source and destination layer 2 address
  - for example the source and destination MAC address if Ethernet is the layer 2 technology
  - switches operates on layer 2
  - the datalink layer defines how data is formatted for transmission and how access to physical media is controlled.
  - it also typically includes error detection and correction to ensure a reliable delivery of the data.
- Layer 1 Physical layer

  - concerns physical components of the network
  - the physical link enables bit transmission between end devices
  - it defines specifications needed for activating , maintaining and deactivating the physical link between end devices.

  ### The CISCO IOS operating systems

  Navigating CISCO command line:
  Router:

  - To see commads at user exec mode type `?`
  - To go to privilege exec mode type `enable`
  - To see comands "starting with" example `di?`, use start letters the question mark, use space to get more context with that command `dir ?`
  - `show` command used lot
  - `debug`
  - global terminal `configure terminal`
  - `ctrl+a` move to start of line
  - if you are at the wrong command level you will also get a _"invalid input at '^' marker"_ , if you get it you can write `do` first
  - command commands: `do show ip interface brief`, ` do show running-config`
  - Exit = go up one

- End = go out to priv exec mode

## OSI Layer 4 - Transport layer

- the transport layer provides transparent transfer of data between hosts and provides end-to end error recovery and flow control.
- flow control is the process of adjusting the flow of data from the sender to ensure the reciving host can handle all of it.
- session multiplexing , multiple sessions
- TCP: connection oriented,

## OSI Layer 3 - Network

- The network layer is responsible for routing packets to their destination and for Quality of service
- IP is the bestknown Layer 3 protocol
- it is a connectionless protocol with no acknowledgements at Layer 3
- Other Layer 3 protocols include ICMP( Internet control message protocol) and IPSec
- the IP Header

- Unicast Traffic: is to a single destination host
- Broadcast Traffic: is to all hosts on the subnet
- Multicast Traffic: is to multiple interested hosts

**Converting from Decimal to Binary**

      256-128-64-32-16-8-4-2-1
      236 = 011101100

**IPv4 Addresses**

- an IPv4 address is 32 bits long
- it is written as a 4 octets in dotted decimal format
- each octet is 8 bits long(4x8 = 32)

**Calculating IPv4 Address Octets in binary**
256-128-64-32-16-8-4-2-1

- convert to binary 129.168.10.15 = 11000000 10101000 00001010 00001111

**The Subnet Mask**

- for a host to send traffic to another host in a different subnet, it must be forwarded by a router
- the host therefor needs to understand if the destination is on the same or a different subnet in order to know how to send it
- 32 bits long and can be written in dotted decimal or slash notation

## IP Address Classes

/8 not many networks but alot of hosts per network
/24 lots of networks but not alot of hosts per network
**Class A**

- **the default subnetmask is /8**
- assigned to networks with a large number of hosts
- The high-order(First) bit in a class A address is always set to zero

- valid network addresses range from 1.0.0.0 to 126.0.0.0 /8
- it allows for 126 networks and 16,777,214 host per network

**Class B and C**
_Class B_

- **the default subnet mask is /16**
- Class B addresses are assigned to medium-sized to large-sized networks.
- the two high order bits in class B address are always set to binary 1 0

- valid network addresses range from 128.0.0.0 to 191.255.0.0 /16
- This allows for 16,384 networks and 65,534 hosts per network
- this would also be subnetted in a real worl environment
  _Class C_
- **The default subnetmask is /24**
- Are used for small networks
- The three high-order bits in a class C address are always set to binary 1 1 0.

- valid nework addresses range from 192.0.0.0 to 223.255.255.0/24
- This allows for 2,097,152 networks and 254 hosts per network.
- This could be allocated as is for a real world network, or subnetted into smaller subnets.

**Class D and E**
_Class D_

- reserved for multicast addresses
- the four high-order bits in the class D address are always set to binary 1 1 1 0
- These addresses are not allocated to hosts and there is no default subnetmask
- address range: 224.0.0.0 to 239.255.255.255

_Class E_

- experemental and reserved for future use

![alt text](assets/IP_classes.png)
