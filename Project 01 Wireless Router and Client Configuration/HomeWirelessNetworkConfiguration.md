# Project 01: Secure Home Wireless Network Configuration
This project demonstrates the step-by-step configuration of a secure home wireless network using Cisco Packet Tracer, focusing on both gateway setup and end-device connectivity.


<img width="430" height="238" alt="image" src="https://github.com/user-attachments/assets/2ee21469-8a35-4da0-b557-5936cfe40cd4" />


## Step 1: Basic Wireless Settings
In the initial phase, I accessed the Wireless Router's GUI to configure the fundamental parameters of the 2.4 GHz band.

Task: Customizing the Network Name (SSID) and ensuring visibility.


<img width="626" height="343" alt="image" src="https://github.com/user-attachments/assets/61cd7ae3-d31d-4fcc-85e4-605f14fab047" />


Description: Configuring basic wireless parameters on the 2.4 GHz band. I have customized the Network Name (SSID) to 'AdemsHomeNetwork' and ensured that SSID Broadcast is enabled for device discovery. The channel settings are set to 'Auto' to prevent interference with other nearby networks.

## Step 2: Implementing Wireless Security (WPA2)
Security is the most critical part of a network. I moved beyond the default settings to protect the network from unauthorized access.

Task: Configuring encryption and a secure passphrase.

<img width="740" height="489" alt="image" src="https://github.com/user-attachments/assets/41b7773c-968b-46b4-b787-1c84c34abfc9" />


Description: Implementing robust wireless security protocols. I have configured the 2.4 GHz band with WPA2-Personal (AES encryption), which is the standard for home network security. A custom passphrase has been set to ensure that only authorized users can access the network, protecting it against unauthorized intrusions.

## Step 3: Client-Side Connection Initiation
After securing the router, I transitioned to the end-device (PC) to begin the connection process.

Task: Using the PC Wireless utility to scan for the network.

<img width="771" height="324" alt="image" src="https://github.com/user-attachments/assets/fa5912b6-566b-4882-b50f-85b6ba9c92af" />



<img width="548" height="476" alt="image" src="https://github.com/user-attachments/assets/e81611fa-e9e6-4fea-8cc6-a538f44ec3e1" />

Description: Configuring the wireless client on the end-device. I am using the 'PC Wireless' utility to scan for available networks and establish a secure connection. This step involves authenticating with the WPA2-Personal passphrase previously configured on the home router to join 'AdemsHomeNetwork'. Scanning for available wireless networks. The client successfully discovered 'AdemsHomeNetwork' with a strong signal strength (97%). I am now initiating the connection process by selecting the SSID and clicking 'Connect', which will prompt for the WPA2-PSK security credentials.

## Step 4: Wireless Authentication
To establish the encrypted link, the client must provide the correct credentials.

Task: Entering the Pre-shared Key (PSK).


<img width="552" height="540" alt="image" src="https://github.com/user-attachments/assets/a7e641ea-1386-4e53-9914-3751f0d23119" />


Description: Finalizing the wireless connection through secure authentication. In this step, I am entering the WPA2-Personal Pre-shared Key (PSK) on the client device. This demonstrates the practical application of the security settings established on the router, ensuring that the connection is encrypted and protected against unauthorized access.

## Step 5: Connection Verification (Infrastructure Mode)
Once the handshake is complete, the status is verified through the Link Information tab.

Task: Confirming successful association with the Access Point.


<img width="568" height="547" alt="image" src="https://github.com/user-attachments/assets/1fd03504-a720-4696-aa5a-d85eb7d1e2fe" />


Description: Verification of successful wireless connectivity. The client device is now fully authenticated and connected to the 'AdemsHomeNetwork' access point. As shown in the 'Link Information' tab, both Signal Strength and Link Quality are at maximum levels, confirming a stable and high-speed connection in Infrastructure Mode.
## Step 6: Final Technical Validation (IPConfig)
The ultimate proof of a functional network is the successful delivery of IP addresses via DHCP.

Task: Validating IP addressing and gateway connectivity.

<img width="762" height="240" alt="image" src="https://github.com/user-attachments/assets/08a9ec7c-6b9b-4fa6-8b96-878f9a86796a" />



Description: Verifying IP addressing and network connectivity using the ipconfig command. The output confirms that the wireless client has successfully obtained a dynamic IPv4 address (192.168.0.102) from the router's DHCP server. The presence of a valid Subnet Mask and Default Gateway (192.168.0.1) ensures that the device is correctly configured to communicate both within the local network and with external networks.
