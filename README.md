# C2 DETECTION
Investigation and incident report on suspected Command-and-Control (C2) traffic.
 Summary

During a packet capture review using Wireshark, suspicious TCP communication was observed from internal IP `10.5.12.22` to external IP `176.65.144.169` over port `7702`. Analysis indicated potential C2 activity.

## 📂 Contents

- `report.pdf` – Full industry-standard incident report
- `/screenshots` – Annotated images of packet captures and threat intelligence
- `2025-05-12-infection-traffic-from-unidentified-malware.pcap` – Network capture file

## 🛠 Skills Demonstrated

- Network traffic analysis (Wireshark)
- Threat intelligence correlation
- Incident response documentation
- TCP stream investigation
  
##   Screenshot Key & Descriptions
  
📸 Screenshot 1: Initial Traffic View in Wireshark
This screenshot captures the initial view of the .pcap file loaded in Wireshark. It shows raw network traffic with various source and destination IPs, protocols, ports, and timestamps.
📝 At this point, the suspicious activity hasn’t been isolated. This view represents the entire captured network traffic, from which potential anomalies need to be identified.

📸 Screenshot 2: Navigating to 'Statistics → Conversations'
In this screenshot, I’ve navigated to Statistics > Conversations, a built-in Wireshark feature used to analyze high-level communication flows. This window displays a list of conversations sorted by endpoint IPs and ports along with their corresponding byte and packet counts.

📝 The goal here was to identify unusually high or repetitive traffic between two endpoints, which could signal malicious behavior or persistent connections like C2.

📸 Screenshot 3: Selecting a Suspicious Conversation
This screenshot shows the Conversations window where I identified and selected the conversation with the highest number of packets between the internal IP 10.5.12.22 and the external IP 176.65.144.169 over TCP port 7702.

📝 The high packet count, unusual port number, and unfamiliar destination IP raised suspicion. From here, I right-clicked and selected “Follow → TCP Stream” to analyze the payload.

📸 Screenshot 4: Analyzing the Followed TCP Stream
The final screenshot displays the TCP stream output, which revealed a sequence of unreadable, likely encrypted or obfuscated data flowing from the internal device to the external IP.

📝 This strongly indicated the presence of Command-and-Control (C2) activity, as the data was not in plain text and didn’t resemble typical service traffic like HTTP, DNS, or SSL.

## 📅 Date of Investigation
21/05/2025
