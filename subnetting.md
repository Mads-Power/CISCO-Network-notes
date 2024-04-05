# Subneting notes

## CIDR CLASSLESS Inter-Domain Routing

- CIDR removed the fixed /8, 16 and /24 requrements for the address classes, and allowed them to be split or subnetted into smaller netwowrks.
- f.eks 175.10.10.0/20
- companies can now be allocated and address range which more closly matches their needs and does not waste addresses

## Default subnets of classes

- Class **A** Default = /8
- Class **B** Default = /16
- Class **C** Default = /24

- To subnet the network into smaller subnets, we need to "borrow" host bits and add them to the network portion of the address.
- The network address line always moves to the right when we subnet
- The further to the righ we go, the more subnets we will have of that size but less hosts

**Formula for subnetting**

- The formula is 2^_subnet-bits_
- example: IF Class C network uses a /28 subnetmask then we have borrowed 4 bits from the default /24. 2^4 = 16 available subnets.
- Example: Class B network uses a /28 subnet mask, borrowed 12 bits from default /16. 2^12 = 4096 available subnets

- 2^4 = 2-4-8-16
- subnets need to go via a router if they want to communicate to eachother.
  **Calculating number of hosts**
- The formula is 2^host-bits minus 2: Class Cnetwork uses a /28 subnetmask we have 4 bits left for hosts: 2^4 - 2 = 14
