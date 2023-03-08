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
