# Intro to Networking and Incident  Management throughout the network

## How Internet works

OC (optical cable ) are connected throught ocean 
WAN (Wide Area network) a network that spans large area
MAN (Metropolitan Area network) which will interconnects multiple LANS
LAN (Local Area Network) a computer network that interconnects devices within limited area

Latency : It is the time taken for data packet to travel from source to destination.
Bandwidth : The maximum amount of data that can travel across the network connection in specific amount time .
Throughput : The actual rate at which data succesfully transferred over a network connection within specific timeframe.

Regions : regions are places at which data centers are placed.

CDN : geographically distributed group of servers that works together to provide fast  delivery of content by storing copies of data in servers close to end users which will reduce the latency.

Edge locations (edge computing) : for caching the data 
Local zones : localzones are used for  edge computing
availability zones : each region has separate isolated data centers each equipped with independent power.

Router : acts as central hub for internet connection, connects multiple networks together, forwards data between different networks.
Switch : forwards packets between group of devices in the same network.

Hub : a hub is central connecting device when it recieves data from one connected device it will blindly breadcasts that data to all other connected devices instead of routing to specific destination.

Racks : designed to house IT equipment like servers , switches and routers it foundational skelton of a data center .

## The addressing for the internet

Ipv4 (four octets each octet represents 8 bits representing in decimal notation ranging from 0 to 255). we use Ipv4 in subnets
Ipv6 (128 bit)
 1 undecillion is equal to 10 power 36

CIDR(classless inter domain range) (2 power (32-n)) (one usage is to create subnets in vpc)
- To know the range of IP addresses .
- 12.33.56.122 /32(1) , 12.34.23.0/0 (2 power 32)
- The last IP which is broadcast IP wont be used due to security risks

some of important cmds :
traceroute google.com
nslookup google.com
learn about dns
## OSI[ISO standards] vs TCP/IP models 

- 7 layers  for OSI and TCP/IP has 4 layers
- application layer(application, presentation,session) , transport layer , internet layer(network layer), network acess layer (data link and physical layer)
- MAC address is physical address assigned to machine
- Transport layer (TCP(3 way handshake) and UDP)
- presentation layer [encrytion and security]
-SSL vs TLS

-Security (Firewall)
- Ingress(incoming traffic )and Egress(outgoing traffic)
- Protocol:IP:port
- vpc , internet gateway , public subnet and private subnet, NAT gateway (hands on)


Cmds usage :

## ping
- To check connectivity (by using ping computer/router/server/any device) you will get echo replying requests.
- logs 
1. request time out server down or firewall is blocking the requests
2. packet loss + request timeout because of network congestion , faulty hardware (bad networkcard , bad cables or modum)
3. Destination host unreachable (remote server down or router unable to route to server or our computer is not connected to network)
4. ping domain_name ( ping request could not find yahoo.com please check the name and try again   and ping ip_ address works fine then its DNS issue  or problem with isp or check DNS configuration with network card)
ipconfig /flushdns [to clear out DNS caching]
5. ping localhost or ping 127.0.0.1 (to check network card is working correctly or not)

## traceroute / tracert

- with ping if you get high average time then we will use tracetoute to check at which router issue lies


## dig
- dig `domainname.com` or nslookup <domainname.com>
- mainly used for DNS issues


## curl
- testing apis / health checking endpoints , downloads artifacts or scripts , network debugging
curl -I google.com


Probing the port scenario :

curl -I http://localhost:80 

succesful output :
`0
HTTP/1.1 200 OK
Server: nginx/1.24.0 (Ubuntu)
Date: Sat, 13 Jun 2026 15:49:32 GMT
Content-Type: text/html
Content-Length: 615
Last-Modified: Wed, 13 May 2026 00:20:22 GMT
Connection: keep-alive
ETag: "6a03c3c6-267"
Accept-Ranges: bytes`

### scenario 1 :
If you see `nc: connect to localhost port 80 (tcp) failed: Connection refused`, it means your networking stack is working fine, but there is no program listening on that port.

### scenario 2 :
`Connection timed out" or Hangs indefinitely`
If the command just sits there spinning and eventually says timed out, it means your request is being silently dropped. The port might be open, but something is blocking you from reaching it.

Next Check: Check your firewall rules. Your local firewall (UFW) might be blocking traffic to port 80.
If UFW is active and port 80 isn't listed as "ALLOW", you'd fix it by running `sudo ufw allow 80/tcp`.

### scenario 3 :
Could not resolve host: localhost
If curl throws an error like Could not resolve host: localhost, it means your machine doesn't know what localhost means. This points to a local configuration issue.

Next Check: Check your /etc/hosts file to ensure 127.0.0.1 is correctly mapped to localhost.
use `cat /etc/hosts`
