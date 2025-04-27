# DDoS Attack Detection and Mitigation Using Wireshark

## Project Overview
This project simulates a **Distributed Denial of Service (DDoS)** attack using **Hping3**, detects the attack using **Wireshark**, 

## Tools Used:
- **Wireshark**: For capturing and analyzing network traffic.
- **Kali Linux**: Attacker system used to simulate the DDoS attack.
- **Hping3**: Tool used to generate a SYN flood (DDoS attack).
- **Apache Web Server**: Victim server to receive traffic.
  

## Steps to Reproduce the Attack :

### 1. **Set Up the Victim Server**
   - Install Apache Web Server on the victim machine.
   - Verify that the web server is running and accessible.

### 2. **Simulate the DDoS Attack**
   - Use `Hping3` to generate a **SYN Flood** attack:
     ```bash
     sudo hping3 --flood --syn -p 80 <victim-ip>
     ```

### 3. **Detect the Attack in Wireshark**
   - Apply Wireshark filters to capture **SYN packets**:
     ```bash
     tcp.flags.syn == 1 and tcp.flags.ack == 0
     ```

## Observations:
- During the attack, there was a significant increase in the number of **SYN packets** with no corresponding **ACK packets**, indicating a typical **SYN flood**.
- **Wireshark** revealed traffic anomalies, including a large number of half-open connections and **duplicate source IPs**.


## Conclusion:
This project demonstrates how to detect and mitigate DDoS attacks using **Wireshark** and basic firewall configurations. It is a valuable hands-on experience for SOC Analysts in understanding network traffic and attack mitigation strategies.
