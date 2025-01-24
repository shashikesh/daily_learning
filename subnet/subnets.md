To calculate the subnet from a `CIDR` (Classless Inter-Domain Routing) notation, you need to understand the relationship between the `network prefix` and the `subnet mask`. 

Here's a detailed explanation and the formula:

### CIDR Basics
- `CIDR Notation`: Represented as A.B.C.D/N, where: 
    - `A.B.C.D` is the base (starting) IP address.
    - `N` is the prefix length *(number of bits used for the network portion)*.
- The remaining bits `(32 - N)` are used for the host portion.
### *Key Calculations*
1. **Subnet Mask**
Convert the CIDR prefix length (N) into a subnet mask:
- The subnet mask is a 32-bit binary number with:
    - `N` bits set to `1` (network bits).
    - `(32 - N)` bits set to 0 (host bits).
For example:

- CIDR: `192.168.1.0/24`
- Prefix Length: 24
Subnet Mask: `11111111.11111111.11111111.00000000` = `255.255.255.0.`
2. **Number of Subnets**
To divide a network into subnets:

- Formula:
    - **Number of Subnets** = `2^new prefix length − original prefix length`
 
For example:
- Original CIDR: `/24`
- Subnet CIDR: `/26`
- Subnets: $2^{26−24}$=4

3. **Number of Hosts per Subnet**
- Formula:
        - Number of Hosts per Subnet= $2^{host bits}$ -2
- Subtract 2 for the network and broadcast addresses.
For example:
- CIDR: `/24`
- Host Bits: 32−24=8
- Hosts: $2^{8}$-2 =254
4. **Subnet Size**
The size of each subnet (in IP addresses):

- Formula:
        Subnet Size = $2^{32-CIDR}$
 
For example:
- CIDR: `/24`
- Host Bits: 32−24 = 8
- Subnet Size: $2{8}$ =256 (including network and broadcast addresses).
5. **Subnet Address Range**
To calculate the range of each subnet:
- Find the **increment:**
        Increment = $2{host bits}$
 
- For example, for /26:
    - Increment: $2^{32-26}$ = 64

- Subnet ranges:

    - 192.168.1.0 - 192.168.1.63
    - 192.168.1.64 - 192.168.1.127
    - 192.168.1.128 - 192.168.1.191
    - 192.168.1.192 - 192.168.1.255.


## Calculate the New Subnet Mask
 
Formula:
```hcl
    New Prefix = Original Prefix + log2(Number of Subnets)
```
- log2(8)=3  
New Prefix=16+3=19
