# Network+ Notes
## Table of contents
* 1.1 [Introduction to IP](https://github.com/HiroNewf/Network-Notes/blob/main/Network%2B%20Notes.md#introduction-to-ip)
* 1.1 [Common Ports](https://github.com/HiroNewf/Network-Notes/blob/main/Network%2B%20Notes.md#common-ports)
* 1.2 [Understand the OSI Model](https://github.com/HiroNewf/Network-Notes/blob/main/Network%2B%20Notes.md#understanding-the-osi-model)
* 1.3 [Introduction to Ethernet](https://github.com/HiroNewf/Network-Notes/blob/main/Network%2B%20Notes.md#introduction-to-ethernet)
## [Introduction to IP](https://www.youtube.com/watch?v=M5c9HdaQqh0&list=PLG49S3nxzAnmpdmX7RoTOyuNJQAb-r-gd&index=3&ab_channel=ProfessorMesser)

- TCP and UDP for moving data across the network
- Frames have many things inside them including headers and data
- Lots of encapsulation when getting a frame ready to move across the network
- TCP is layer 4
    - Uses the TCP handshake
    - A connection based protocol
    - Good when you need to make sure you get all of the data
- UDP is layer 4
    - Does not verify that data has been received
    - Faster but less reliable (Connection less protocol)
    - Good for real time purposes like voice/video calls, ect
- IP addresses and port numbers is what is used so the routers and other devices know where to direct the frame/data so that the right person may get their information
- Many different applications have their own ports
    - SHH - 22
    - HTTPS 443
    - ect
- All of this routing data like source and destination IP and ports will be stored in the frame
- 0-1023 are permanent port numbers while 1,024-65535 are non permanent port numbers
- TCP ports and UDP ports are different things
- ICMP (Internet Control Message Protocol)
    - Used to check in and see if a device is functioning properly
    - Admin use mainly
    - Also can be used for devices to alert others when they are not working properly
    - Could alert that a packet timed out and did not reach its destination

## [Common Ports](https://www.youtube.com/watch?v=vp_ZxQ0CTJk&list=PLG49S3nxzAnmpdmX7RoTOyuNJQAb-r-gd&index=4&ab_channel=ProfessorMesser)

- Telnet TCP 23
    - Remote login via console
    - Not encrypted so not at all secure
    - Not used often
- SHH TCP 22
    - Encrypted remote login via console
    - Better than Telnet
- DNS UDP 53
    - Converts names of websites to IP addresses
    - Very important, if they aren’t working they whole network will have trouble
- SMTP TCP 25
    - Server to server email transfer
    - Send from a device to a mail server
- SFTP TCP 22
    - Uses SSH to make secure file transfer
    - Full featured file transfer protocol
- FTP TCP 20 (active mode data) TCP 21 (Control)
    - An unencrypted file transfer protocol
    - Username and password needed
    - Full featured
- TFTP TCP 69
    - No authentication or encryption
    - Just read and write files, very basic
- DHCP UDP 67 and UDP 68
    - Automatically configures IP address, default gateway, subnet mask, ect
    - DHCP could be stand alone or more commonly for houses in the router
    - There is a lease time for IP addresses, you only get it for a certain amount of time
    - Reservations can make it so certain devices always get the same IP addresses
- HTTP TCP 80
    - Unencrypted protocol commonly used via a browser
- HTTPS 443
    - Encrypted browser protocol
- SNMP UDP 161
    - Managing network devices, gather logs and statistics from the devices
    - V1 & V2 not encrypted, V3 is encrypted, has integrity, authentication and authorization
- RDP TCP 3389
    - Remotely share a desktop (or just an application)
    - Common for Windows
    - Can use other OS for this as well
- NTP UDP 123
    - Sync all the clocks
    - Very accurate
- SIP TCP 5060-5061
    - Voice over IP
    - Setups up and ends calls
    - Adds features as well
- SMB also called CIFS, TCP 445
    - Used by Windows
    - Files sharing, printer sharing, ect
- POP3 TCP 110
    - Receive emails from a mail server
    - Basic
- IMAP4  TCP 143
    - More common today
    - Receive emails from a mail server
    - More features than POP3
- LDAP TCP 389
    - Directory access protocol
    - Store and retrieve info in a network directory
- LDAPS TCP 636
    - LDAP but over SSL, so secure
- H.323 TCP 1720
    - Another VoIP signaling protocol
    - Call, ring, hangup
    - Early VoIP protocol, but still used quite a lot today

## [Understanding the OSI Model](https://www.youtube.com/watch?v=G7aVKgGUe9c&list=PLG49S3nxzAnmpdmX7RoTOyuNJQAb-r-gd&index=5&ab_channel=ProfessorMesser)

- Open Systems Interconnection Reference Model
- 7 Layers
    - Layer 7 Application (The layer we see, HTTP, FTP, POP3, ect)
    - Layer 6 Presentation (encoding and encryption, often combined with layer 7)
    - Layer 5 Session (Communication management between devices, control protocols and tunneling protocols)
    - Layer 4 Transport (TCP, UDP, ect)
    - Layer 3 Network (Routing layer, routers, IP, Packets, Layer 3 switches, frame fragmentation)
        - Frame fragmentation is when you break a frame into smaller pieces so the data can be sent across the network
    - Layer 2 Data Link (MAC, Frames, Switches, Bridges)
    - Layer 1 Physical (Signaling, cabling, connectors, hubs, bits, ect)
- Certain protocols and processes exists at each layer
- Packet capture tools like Wireshark are where you really start to see OSI model in the real world

## [Introduction to Ethernet](https://www.youtube.com/watch?v=iXfBbs9SSFQ&list=PLG49S3nxzAnmpdmX7RoTOyuNJQAb-r-gd&index=6&ab_channel=ProfessorMesser)

- Enterprise networks have the same base functionality has a home network
    - There is just a ton more data and hardware
    - May even be many building connected to each other
- MAC addresses
    - Physical unique address
    - 48 bits long, displayed in hexadecimal
        - First half is the Organizationally Unique Identifier (the manufacturer)
        - Second half is Network Interface Controller Specific (serial number)
- Half duplex
    - Cannot send and receive at the same time (like hubs or switches if configured as so)
    - Prone to collisions
    - CSMA/CD Can tell when there is a collision and wait a random amount of time before continuing to send data
    - CSMA/CD can see if any data is currently being transmitted or if the case is clear
- Full duplex
    - Can send and receive at the same time
    - Need to make sure the switch and devices support full duplex
    - Much more intelligent in many ways (Knows where the data needs to go instead of just sending it to everyone on the network)
- CSMA/CA
    - Collision Avoidance, like CD but for wireless networks
    - Can’t hear the other devices so they will ask if the network is in the clear before sending data
## [Network Switching Overview](https://www.youtube.com/watch?v=jR3VoKZWJyc&list=PLG49S3nxzAnmpdmX7RoTOyuNJQAb-r-gd&index=7&ab_channel=ProfessorMesser)

- The switch is much smart than the hub
    - Forward or drop frames based on the MAC addresses
    - Has a table MAC addresses
    - Keeping the environment loop free with STP
- Frame switching
    - Has a table of MAC dresses to output interface
    - Only knows the next step, just keeps passing the packet on until it gets to its location or its TTL expires
    - Always adding to its table when it come across something new
        - If it doesn’t know where to send the data it floods the data to all of the devices
            - When the data finds the right person the switch gets a response and adds the information to it’s table
- ARP
    - Determine MAC address based on a IP address
    - Can be captured with a packet capture tool
    - arp -a to view the arp table on your computer
