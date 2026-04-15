# Observe Traffic Flow in a Routed Network
<img width="834" height="410" alt="image" src="https://github.com/user-attachments/assets/0c422efc-142a-4551-9a7c-75cae4b26693" />

## Part 1: Observe Traffic Flow in an Unrouted LAN
In this part, you will use Packet Tracer simulation mode to observe how traffic flows through an unrouted LANs.

##### Step 1: Clear the ARP cache on host Sales 1.
- Hover your mouse over the Sales 1 host to see its IP address. Make note of it.
  <img width="989" height="226" alt="image" src="https://github.com/user-attachments/assets/866f79ad-cb60-4165-a742-9e931d56327b" />
- Click Sales 1 > Desktop tab > Command Prompt, and then enter the arp -a command. There should be no MAC addresses in the ARP cache. If there are entries in the ARP cache, use the arp -d command to delete them.
 <img width="726" height="334" alt="image" src="https://github.com/user-attachments/assets/94daa096-dbe4-43ba-9456-6f79911ac521" />

##### Step 2: Observe traffic flow in the network.
- Click the Simulation mode button in the lower right-hand corner of the PT window to switch from Realtime to Simulation mode.
  <img width="1348" height="477" alt="image" src="https://github.com/user-attachments/assets/f7fb1e3f-7c83-4266-bc64-0590cc1290e5" />
- Open the Command Prompt for Sales 2, and then enter the ping command followed by the IP address of Sales 1.
 <img width="760" height="321" alt="image" src="https://github.com/user-attachments/assets/d14fdecf-e42d-46b7-8c79-458e6d169753" />
 -Use the Capture then Forward button (the triangle pointing to the right with a vertical bar attached) in the Play Controls of the Simulation Panel to begin to execute the ping command. You will see a colored envelope icon appear next to Sales 2. This represents a PDU. Click the Capture then Forward button to move the PDU to the first device on its path to the destination device. Click the PDU envelope to inspect the contents.
  As we see in the below packet travel all the department, and making unnecessary trafic
  Even though the destination for the ping requests may be adjacent to the requesting source, if the host has an empty ARP cache, an ARP request is sent that must be processed by every host on the network. ARP cache entries are removed after a preset period of time. With many hosts on a network, ARP broadcasts will be issued more frequently. This requires network resources to be taken away for the work-related traffic.
  <img width="1314" height="443" alt="image" src="https://github.com/user-attachments/assets/553096c9-6f9c-4fd5-8a9c-8f212f966258" />
  <img width="1332" height="425" alt="image" src="https://github.com/user-attachments/assets/b3ace992-0d3e-44ee-af6b-597b5f3e8870" />

## Part 2: Reconfigure the Network to Route Between LANs.
In this part, you will demonstrate the benefits of routing between department networks. First, you will cable each network switch to connect directly to a router interface. Then, you will reconfigure the hosts to receive addresses on two new IPv4 networks that are created by the router.

### Step 1: Change device connections.

- For the cable that connects the Accounting switch with Finance switch, click the green triangle on the Accounting switch side of the link.
- Drag that end of the cable to the Edge router and connect the cable to port GigabitEthernet 1/0.
<img width="843" height="399" alt="image" src="https://github.com/user-attachments/assets/6cf91ccf-5ecc-4c72-ac4f-eab5599a95b7" />

- Repeat this step for the link between Finance and Sales. Connect to the available GigabitEthernet port.
<img width="822" height="404" alt="image" src="https://github.com/user-attachments/assets/78cfd698-4674-4e37-9ceb-48b108515210" />

### Step 2: Configure the hosts with addresses on the new LANs.
Each interface of the Edge router was previously configured to put each department on its own IPv4 network. The hosts will receive their new IP addresses from the router. However, it will take time for the hosts on the Finance and Sales networks to receive their new IP addresses. (The hosts on the Accounting network will remain on 192.168.1.0/24.)

- To speed up the process of getting new IP addresses, open a Command Prompt on each of the four devices in the Finance and Sales networks
- Enter the ipconfig /renew command. This will force the host to request a new IP address from the DHCP server that is running on the Edge router. You should see confirmation of new IP addressing.
<img width="841" height="308" alt="image" src="https://github.com/user-attachments/assets/2de48718-e7bf-4458-b67c-571dcaaae36c" />

## Part 3: Observe Traffic Flow in the Routed Network.
In this part, you will observe how traffic now flows through a routed network.

##### Step 1: Ping Sales 1 from Sales 2.

- Return to the Command Prompt for Sales 2 and verify that its ARP cache is empty. If it is not, delete any entries.
- Switch to Simulation mode.
- Ping Sales 1 from Sales 2.
  <img width="742" height="237" alt="image" src="https://github.com/user-attachments/assets/d2782d4f-676a-4fc4-9265-e094296fcb25" />

- Use the Capture then Forward button to step the PDUs through the network. Observe how the ARP request message flows through the network this time.
Only Sales 1 and the router interface that is connected to the Sales department network process the PDU devices receive the ARP broadcasts this time.
<img width="1338" height="469" alt="image" src="https://github.com/user-attachments/assets/8fc1418c-9ab0-4c3c-a7e6-6fdbcbec81c8" />
<img width="1339" height="468" alt="image" src="https://github.com/user-attachments/assets/16daa824-66c7-4261-bbe9-2fdcfc11986b" />


