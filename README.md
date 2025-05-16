# BASH-SCRIPT
# IP Sweeper (Bash-Based)

This project is a basic implementation of a Bash-based IP sweeper tool. Created by *DolapotheEthicalHacker*, it scans all IP addresses from .1 to .254 within a given subnet and reports which ones are online using ping.

##  Features

- Simple Bash script for local network scanning  
- Scans Class C subnets (e.g. 192.168.1.0/24)  
- Detects live hosts using ICMP (ping)  
- Lightweight and runs entirely in the terminal  
- Easy to modify or extend for advanced network automation

##  File

- ipsweep.sh: The Bash script that contains the IP scanning logic.

##  Requirements

No extra tools are required beyond standard Linux utilities. The script uses:

- bash: The shell interpreter
- ping: For sending ICMP echo requests
- grep, cut, and tr: For filtering the output

This makes it ideal for environments like Kali Linux or other Unix-based systems.

##  How the Script Works

Here's what the script does:

1. *Checks if a subnet argument was provided:*  
   If not, it shows an error and usage message.
   
2. *Loops through all IPs from 1 to 254:*  
   It appends numbers 1–254 to the subnet (e.g. 192.168.1) to form full IPs.

3. *Sends one ping to each IP address:*  
   It looks for a successful response (64 bytes) using grep.

4. *Extracts the responding IP address:*  
   Using cut and tr, it cleans and displays only the live IPs.

##  How to Run

Make the script executable:

bash
chmod +x ipsweep.sh


Then run the script like this:

bash
./ipsweep.sh 192.168.1


This will scan 192.168.1.1 to 192.168.1.254.

If no IP is entered, you’ll see:

bash
You forgot an ip address
Syntax: ./ipsweep.sh <ip>


###  Example Output


192.168.1.1
192.168.1.3
192.168.1.11
...


These are the IPs that responded to the ping and are considered *live* on your network.

##  Customization

You can modify or extend this script by:

- Adding a timeout or -W flag to speed up ping response
- Saving output to a file:
  bash
  ./ipsweep.sh 192.168.1 > live_hosts.txt
  
- Adding a hostname lookup using nslookup or host
- Using nmap for advanced scanning

##  Author

*DolapotheEthicalHacker*

---

Feel free to fork or contribute to improve this tool!
