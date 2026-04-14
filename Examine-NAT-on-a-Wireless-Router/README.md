## Examine NAT on a Wireless Router
### Objectives
Examine NAT configuration on a wireless router
Set up 4 PCs to connect to a wireless router using DHCP
Examine traffic that crosses the network using NAT

### Part 1: Examine the configuration for accessing external network.

##### Add 1 PC and connect it to the wireless router with a straight-through cable. Wait for all link lights to turn green before moving onto the next step or click Fast Forward.
<img width="901" height="292" alt="image" src="https://github.com/user-attachments/assets/49f59e8e-b527-43e6-bf0a-e0f022ba1250" />

##### On the PC, click Desktop. Select IP Configuration. Click DHCP to enable each device to receive an IP address via the DHCP on the wireless router.
<img width="1119" height="630" alt="image" src="https://github.com/user-attachments/assets/b19f17eb-2eb1-4980-9054-d1323a93920c" />

##### Navigate to the web browser and enter the IP address of the default gateway in the URL field. Enter the username admin and password admin when prompted.
<img width="1358" height="660" alt="image" src="https://github.com/user-attachments/assets/29d916b8-2bae-48cf-a15f-a0a21c4c7022" />

##### Click Status menu option in the upper right-hand corner. When selected, it displays the Router sub-menu page. Scroll down the router page to the internet connection option. The IP address assigned here is the address assigned by the ISP.
<img width="891" height="689" alt="image" src="https://github.com/user-attachments/assets/b65f58e4-3771-44ad-8802-60a97d5b18b4" />

### Part 2: Examine the configurations for accessing the internal network.

##### Click Local Network within the Status sub-menu bar. Scroll down to examine the Local Network information. This is the address assigned to the internal network. Scroll down further to examine the DHCP server information, and range of IP addresses that can be assigned to connected hosts.
<img width="838" height="583" alt="image" src="https://github.com/user-attachments/assets/8418234b-916d-4727-b8eb-2c344bfab237" />


### Part 3: Connect 3 PCs to the wireless router.

##### Add 3 more PCs and connect them to the wireless router with straight-through cables.
<img width="805" height="436" alt="image" src="https://github.com/user-attachments/assets/bbbf8a77-3287-4fbd-a33c-fe56e841bb29" />

##### Click Command Prompt to verify each device IP configuration using ipconfig /all command.
Note: These devices will receive a private address. Private addresses are not able to cross the internet, therefore, NAT translation must occur.
<img width="1303" height="672" alt="image" src="https://github.com/user-attachments/assets/7cea1a3b-d8e3-4780-9ebe-7af76276798c" />

## Part 4: View NAT translation across the wireless router.

##### Enter Simulation mode by clicking the Simulation tab in the lower right-hand corner. The Simulation tab is located next to the Realtime tab and has a stopwatch symbol. View traffic by creating a Complex PDU in Simulation mode: From the Simulation Panel, click Show All/None to change visible events to none. Now click Edit Filters and under the Misc tab checkmark the boxes for TCP and HTTP. Close the window when done.
<img width="1362" height="707" alt="image" src="https://github.com/user-attachments/assets/ad1ff570-7ff6-4c71-ae51-0556dcf6ea1a" />

##### Add a Complex PDU by clicking on the opened envelope located in upper menu. Click one of the PCs to specify it as the source.
<img width="1364" height="609" alt="image" src="https://github.com/user-attachments/assets/d7518055-906c-438a-a603-7e5ce999f172" />

##### Specify the Complex PDU settings by changing the following within the complex PDU window:
- Under PDU Settings > Select Application should be set to: HTTP.
- Click ciscolearn.nat.com server to specify it as the destination device.
- For the Source Port, enter 1000.
- Under Simulation Settings, select Periodic. Enter 120 seconds for the Interval.
- Click Create PDU in the Create Complex PDU window.
<img width="1365" height="608" alt="image" src="https://github.com/user-attachments/assets/5d3f71e4-6d96-491c-9534-d3e65134caf9" />

##### Double click the simulation panel to unlock it from the PT window. This allows you to move the simulation panel to view the entire network topology.
- Observe the traffic flow by clicking Play in the simulation panel. Speed up the animation by sliding the play control slider to the right.
Note: Click View Previous Events when the Buffer Full message is displayed.
<img width="1364" height="546" alt="image" src="https://github.com/user-attachments/assets/37ef6941-3746-492d-a68a-e035f3f4ae3c" />

## Part 5: View the header information of the packets that traveled across the network.

##### Examine the headers of the packets sent between a PC and the web server.
- In the Simulation Panel, double click the 3rd line down in the event list. This displays an envelope in the work area that represents that line.
- Click the envelope in the work area window to view the packet and header information.
<img width="1365" height="611" alt="image" src="https://github.com/user-attachments/assets/ccbb56d1-0226-4a17-a5e5-05845f1d8be4" />

##### Click the Inbound PDU details tab. Examine the packet information for the source (SRC) IP address and destination IP address.
- Inbound: The computer with the IP address 192.168.1.100 (PC0) created a packet destined for an external web server (209.165.200.228) and sent it to the Wireless Router.
- Inspection: Upon receiving the packet, the router read the information displayed in the "Inbound PDU Details" screen you are currently viewing. It identified the Source IP (PC0) and Destination Port 80 (HTTP/Web request).
- Processing: The router determined whether this packet was allowed to pass through and decided on its next destination.
<img width="492" height="579" alt="image" src="https://github.com/user-attachments/assets/f230e1bc-2137-48c2-bc9e-a85b854a6978" />

##### Click the Outbound PDU details tab. Examine the packet information for the source (SRC) IP address and destination IP address. Notice the change in SRC IP address.
The Wireless Router performed the following operations while forwarding the packet from the internal network to the outside world (the internet):
- IP Address Change (NAT): This is the most significant change. While the Source IP in the "Inbound" section was $192.168.1.100$, you can now see in the "Outbound" section that the Source IP is $209.165.200.227$. The router stripped away the computer's private IP and stamped its own public IP onto the packet.
- Constant Destination: The ultimate destination of the packet (Destination IP: $209.165.200.228$) remained unchanged; the destination for this "letter" is still the same web server.
- Layer 2 Update (Ethernet): To send the packet to the next hop (Cluster/Cloud), the router updated the MAC addresses in the Ethernet header. The Source MAC is now the router’s external interface, and the Destination MAC is the address of the next device.
- Result: The router didn't just act as a bridge; it also provided the packet with a valid "public identity" (via the NAT process) so it could travel across the internet and then dispatched it onto the next cable (GigabitEthernet1).
<img width="487" height="580" alt="image" src="https://github.com/user-attachments/assets/f93d7ef6-e584-42fa-a791-40c8c741eedb" />

