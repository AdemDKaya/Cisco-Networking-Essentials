# Project 01: Secure Home Wireless Network Configuration
This project demonstrates the step-by-step configuration of a secure home wireless network using Cisco Packet Tracer, focusing on both gateway setup and end-device connectivity.
<img width="430" height="238" alt="image" src="https://github.com/user-attachments/assets/2ee21469-8a35-4da0-b557-5936cfe40cd4" />


## Step 1: Basic Wireless Settings
In the initial phase, I accessed the Wireless Router's GUI to configure the fundamental parameters of the 2.4 GHz band.

Task: Customizing the Network Name (SSID) and ensuring visibility.

Description: "Configuring basic wireless parameters on the 2.4 GHz band. I have customized the Network Name (SSID) to 'AdemsHomeNetwork' and ensured that SSID Broadcast is enabled for device discovery. The channel settings are set to 'Auto' to prevent interference with other nearby networks."

## Step 2: Implementing Wireless Security (WPA2)
Security is the most critical part of a network. I moved beyond the default settings to protect the network from unauthorized access.

Task: Configuring encryption and a secure passphrase.

Description: "Implementing robust wireless security protocols. I have configured the 2.4 GHz band with WPA2-Personal (AES encryption), which is the standard for home network security. A custom passphrase has been set to ensure that only authorized users can access the network, protecting it against unauthorized intrusions."

## Step 3: Client-Side Connection Initiation
After securing the router, I transitioned to the end-device (PC) to begin the connection process.

Task: Using the PC Wireless utility to scan for the network.

Description: "Scanning for available wireless networks. The client successfully discovered 'AdemsHomeNetwork' with a strong signal strength (97%). I am now initiating the connection process by selecting the SSID and clicking 'Connect', which prompts for the security credentials."

## Step 4: Wireless Authentication
To establish the encrypted link, the client must provide the correct credentials.

Task: Entering the Pre-shared Key (PSK).

Description: "Finalizing the wireless connection through secure authentication. In this step, I am entering the WPA2-Personal Pre-shared Key (PSK) on the client device. This ensures the connection is encrypted and authorized based on the router's security policies."

## Step 5: Connection Verification (Infrastructure Mode)
Once the handshake is complete, the status is verified through the Link Information tab.

Task: Confirming successful association with the Access Point.

Description: "Verification of successful wireless connectivity. The client device is now fully authenticated and connected in Infrastructure Mode. As shown, both Signal Strength and Link Quality are at maximum levels, confirming a stable connection."

## Step 6: Final Technical Validation (IPConfig)
The ultimate proof of a functional network is the successful delivery of IP addresses via DHCP.

Task: Validating IP addressing and gateway connectivity.

Description: "Verifying network connectivity using the ipconfig command. The output confirms that the client successfully obtained a dynamic IPv4 address (192.168.0.102) from the DHCP server. The presence of a valid Subnet Mask and Default Gateway (192.168.0.1) ensures the device is ready for both local and external communication."
