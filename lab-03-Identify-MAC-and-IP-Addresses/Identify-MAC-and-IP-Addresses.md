## Identify MAC and IP Addresses
In this Packet Tracer activity, you will inspect Ethernet frames and IP packets at different points in the network as they travel from source to destination. 
You will focus on the way that the MAC and IP addresses change depending on the destination (local or remote) and the place where the PDUs are captured.
<img width="558" height="420" alt="image" src="https://github.com/user-attachments/assets/468bb5b9-bc79-4aba-9b38-9e4ca8d5ff38" />

### Part 1: Gather PDU Information for a Local Network Communication
 how a device on a local network does not need a default gateway to communicate with another device on the same local network.

 ##### Click host 172.16.31.3 and open the Command Prompt. Enter the ping 172.16.31.2 command. This command will issue a series of ICMP echo request packets to the destination. If the packets reach the destination, it will send echo-reply messages pack to the source of the ping requests.
 <img width="965" height="642" alt="image" src="https://github.com/user-attachments/assets/e37dec3c-de22-4f3c-96ab-14055774269b" />

 ##### Click the Simulation mode button to switch to simulation mode. Repeat the ping 172.16.31.2 command. An envelope icon that represents a PDU appears next to 172.16.31.3.
 <img width="1022" height="469" alt="image" src="https://github.com/user-attachments/assets/7868c87b-cc2d-4b8f-b135-e8c6a65055be" />

 ##### Click the PDU and locate the following information in both the OSI Model and Outbound PDU Details tabs. The Outbound PDU Details tab shows simplified packet and frame headers for the PDU. You should observe the following details regarding addressing for the PDU.
- At Device: 172.16.31.3
- Source MAC Address: 0060.7036.2849
- Destination MAC Address: 000C:85CC:1DA7
- Source IP Address: 172.16.31.3
- Destination IP Address: 172.16.31.2
 <img width="849" height="535" alt="image" src="https://github.com/user-attachments/assets/c612a0ec-85b4-467d-8b26-7dff58656fd5" />

 ##### Click Capture / Forward (the right arrow followed by a vertical bar) and the PDU moves to the next step in its journey. Use the OSI model tab to gather the same information from Step 1d. Repeat this process until the PDU reaches its destination. For each step on the path to delivery
-  You will notice that the information for the inbound PDU is unchanged.
 <img width="1351" height="596" alt="image" src="https://github.com/user-attachments/assets/b2bfefad-cc2d-49e4-9684-92984103b3b5" />

## Part 2: Gather PDU Information for a Remote Network Communication
To communicate with remote networks, a gateway device is necessary. The gateway device connects two or more networks together. the process that takes place when one device communicates with another device that is on a remote network. Pay close attention to the MAC addresses used.
As a packet moves from one network to another, the Destination IP never changes; however, at every router hop, the Source MAC address is updated with the address of the exit interface, and the Destination MAC address is updated with the address of the next hop.

##### Move your mouse over the Router. You will see information about the addressing of the router interfaces. Refer to these addresses as you observe the PDU flow through the router.
<img width="1200" height="434" alt="image" src="https://github.com/user-attachments/assets/c6637653-ec53-490a-a145-757792255f08" />

##### Return to the Command Prompt for 172.16.31.3. Enter the ping 10.10.10.2 command. The first couple of pings may time out.
<img width="984" height="670" alt="image" src="https://github.com/user-attachments/assets/d36b18cd-ed86-4070-afca-88c6e5921ad1" />

##### Switch to Simulation mode and repeat the ping 10.10.10.2 command. A PDU appears next to 172.16.31.3.
<img width="1068" height="447" alt="image" src="https://github.com/user-attachments/assets/7a65765d-8f56-4973-9566-aa82f4c1ad1d" />

##### Click the PDU and note the following information tab:
- At Device: 172.16.31.3
- Source MAC Address: 0060.7036.2849
- Destination MAC Address: 00D0:BA8E:741A
- Source IP Address: 172.16.31.3
- Destination IP Address: 10.10.10.2
  <img width="812" height="447" alt="image" src="https://github.com/user-attachments/assets/298ebb8a-7948-45e1-8147-8c912734e2cf" />

#####  Click Capture / Forward (the right arrow followed by a vertical bar) to move the PDU to the next device. Gather the same information from Step 1d. Repeat this process until the PDU reaches its destination.
<img width="1017" height="468" alt="image" src="https://github.com/user-attachments/assets/753ddc27-ada7-4ebd-ac7d-72937261859c" />

##### Packet Entering the Router (Inbound)
- Source IP: 172.16.31.3 (Host)
- Destination IP: 10.10.10.2 
- Destination MAC: 00D0.BA8E.741A (FastEthernet1/0 - comes from this door)
<img width="893" height="447" alt="image" src="https://github.com/user-attachments/assets/05d4557f-edc3-46cd-aa93-46abff83f4d8" />
##### Packet Leaving the Router (Outbound)
- Source MAC: 00D0.588C.2401 (The address of FastEthernet0/0). Because the packet is now "departing" from this port.
- Destination MAC: 0060.2F84.4AB6 (The MAC address of the destination device, i.e., 10.10.10.2). 
<img width="1162" height="560" alt="image" src="https://github.com/user-attachments/assets/c3fc567e-fe9a-4576-940b-4684ca9f83df" />




