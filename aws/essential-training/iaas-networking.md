# Networking 

## VPC (AWS VPCs)
* Virtual private cloud
* Allowe servers to talk to each other privately, not connected to the internet
* public subnets handle outside traffic, where private is fully protected from the internet
* /16 is a net mask 0.0 to 255.255
* Chop up vpc with subnet /24 ip range 1.0 -> 1.255

## Internet and NAT gateways

### NAT
* Network Address Translator (NAT)
* Router like a door with inside handle, computer opens a door, instances can have access to the internet

### Internet Gateway
* Door with both handles

## Elastic IPs
* Need IP to stay the same assign elastic ips. release the eleastic ip if you no longer need it

## VPN
* Virtual private network

### AWS Client VPC
* Can talk to VPC, secure tunnel straight to VPC.

### AWS Site to Site VPN
* Bridge on prem with VPC, cloud migration or hybrid module

## ELB
* Elastic Load Balancer, splits up traffic and balancing between applications
* If server goes down takes out, or healthy one is given a break to do downloads

### Network Load Balances
* fast but not many features

### Application Load Balancers
* more features, great for web traffic, not as fast

## DNS (Route 53)
* Phone book of the internet, all go over route 53

