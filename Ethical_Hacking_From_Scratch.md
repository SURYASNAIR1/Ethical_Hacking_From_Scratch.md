# Foot Printing and Reconnaissance

- Footprinting refers to the process of gathering information about a target system. It is the first step of an attack in which the attackers tries to learn as much as possible about the target to find a way to break into the system.

# Types of Footprinting
- Passive footprinting: Collecting information without interacting with the target directly. This is used when information gathering must not be detected by the target. Victim will not recognize that we have gathered some information about the target machine.

- Active footprinting: Collecting information by ineracting with the target directly. With this type of footprinting there is a chance that the target becomes aware of the information gathering.

# Attackers use footprinting to collect the following information:
- Network information
  
   - Domains
 
   - Subdomains
 
   - IP addresses
 
   - Whois and DNS records

 - System information

  - Web server od

  - server locations

  - Users

  - Passwords

- Organization information

 - Employee information

 - Organization's background

 - Phone numbers

 - Locations

# Objectives of Footprinting

- Learn security posture analyze the security posture of the target, find loppholes, and create an attack plan

- Identify focus area using different tools and techniques, narrow down the range of IP addresses

- Find vulnerabilities use the collected information to identify weaknesses in the target's security

- Map the network graphically represent the target's network and use it as a guide during the attack

# How to gather active information
1. Ping: ping command send packet to a remote machine. If the remote machine is alive he will actually send back response to the attacker.

eg: ping 192.168.18.25 OR 

ping -c 5 192.168.18.25 ---> we are specifying the number of packets here

- If the system is responding as unresponsive or destination host unreachable it can be because of :
  
   - Destination computer is not responsive may possibly still booting up a turn off or the OS has been crashed.
     
   - It is unplugged from the network or there is a faulty network device across the path.
 
   - The third reason could be that a firewall is configured to block such packets.

2. traceroute: The traceroute commands trace the routes taken by the packets from your system to another.

- The purpose of taceroute is to find the IP addresses of routers or hopes point to be noted.

eg: traceroute google.com --> we can see the number of hopes

traceroute -I google.com --> this will switch along race road

3. telnet: teletype network protocol.

- By this command we can communicate with a remote machine via command line interface. This command use TELNET protocol.

- The communication happens in clear text.

- Thus this is the weak point of the protocol.

- There is no encryption occured on this protocol.

- eg: telnet 10.10.48.236 80 and while running just press ^ or anyother key for stop the running and then type GET / HTTP/1.1 and hit enter. Now we can see the victim server.

4. Netcat or nc:  Supports TCP and UDP protocols.

- It can function as a client that connects to a listening port.

- Alternatively it can act as a server that listens on a port of your choice.

- Convenient tool that can use as a simple client or server over TCP or UDP. 

- eg: nc -v -n -z 192.168.18.25 20-90 

Here we can see the port is open or not in the specified area (20-90)

**Note:** 192.168.18.25 will be the target machine ip address
-v is verbose, -n is numeric, -z is indicate IO modes is used for scanning.

- Using netcat we can transfer different file from one machine to another.

- Eg: cat > netact.txt
  Then type Hi
  nc -nlvp 5555 < netcat.txt
  check if the file reached the next machine
  on the another machine type nc 192.168.18.28 5555 > netcat.txt
  Now we can see the file got transferred
  To see the contents present inside the copied file type
  cat netcat.txt

- nc 192.168.18.25 21 --> to see the banner the o/p i got is welcome to fttp server. Means we successfullt identified port number 21 of target machine.
