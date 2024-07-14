# Subneting notes

## CIDR CLASSLESS Inter-Domain Routing

- CIDR removed the fixed /8, 16 and /24 requrements for the address classes, and allowed them to be split or subnetted into smaller netwowrks.
- f.eks 175.10.10.0/20
- companies can now be allocated and address range which more closly matches their needs and does not waste addresses

## Default subnets of classes

- Class **A** Default = /8 = 255.0.0.0 = 11111111.00000000.00000000.00000000
- Class **B** Default = /16 = 255.255.0.0 = 11111111.11111111.00000000.00000000
- Class **C** Default = /24 = 255.255.255.0 = 11111111.11111111.11111111.00000000

- To subnet the network into smaller subnets, we need to "borrow" host bits and add them to the network portion of the address.
- The network address line always moves to the right when we subnet
- The further to the righ we go, the more subnets we will have of that size but less hosts

**Formula for subnetting**

- Calculating CIDR Notation( / notation) = The Decimal subnetmask (eks: 255.255.255.0), convert this to binary = 11111111.11111111.11111111.00000000 (from example) , then count 1's = 24 = CIDR notation =/24
- The formula is 2^_subnet-bits_
- example: IF Class C network uses a /28 subnetmask then we have borrowed 4 bits from the default /24. 2^4 = 16 available subnets.
- Example: Class B network uses a /28 subnet mask, borrowed 12 bits from default /16. 2^12 = 4096 available subnets

- 2^4 = 2-4-8-16
- subnets need to go via a router if they want to communicate to eachother.
  **Calculating number of hosts**
- The formula is 2^host-bits minus 2: Class C network uses a /28 subnetmask(/24 is normal) we have 4 bits left for hosts: 2^4 - 2 = 14


### Subnetting practice questions
1.  what are the network address, broadcast address, adn valid host addresses form the IP address 198.22.173/26
2.  What is the subnet mask in dotted decimal notation
  ANSWER: 
  1. Dotted Decimal: /26 borrows the first 2 bits in the last octet
![alt text](/assets/ip_cidr.png)
![alt text](/assets/cidr_ips2.png)


### Private addresses
RFC 1918 Private Addresses
There is a range of private addresses in each address class.
A: 10.0.0.0 – 10.255.255.255
‒ 10.0.0.0/8
‒ 10.0.0.0 255.0.0.0
B: 172.16.0.0 – 172.31.255.255
‒ 172.16.0.0/12
‒ 172.16.0.0 255.240.0.0
C: 192.168.0.0 – 192.168.255.255
‒ 192.168.0.0/16
‒ 192.168.0.0 255.255.0.0