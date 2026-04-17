# Network Delay Measurement Tool (SDN/Mininet Project)

## Problem Statement
Measure and analyze network latency between hosts using ping, record RTT values, compare delays across paths, and analyze delay variations.

---

## Objective
This project aims to:
- Measure network delay using ICMP ping
- Record RTT (Round Trip Time) values
- Compare latency across different paths
- Analyze delay variations under different network conditions

---

## Technologies Used
- Mininet (Network Emulator)
- Linux Networking Tools (ping, tc)
- Python (optional automation)
- Open vSwitch

---

## Network Topology
Linear topology with 3 hosts:
h1 -- s1 -- h2 -- s2 -- h3


---

## Setup Instructions

### 1. Install Mininet

    sudo apt update
    sudo apt install mininet -y

## How to Run 

### Step 1: Start Mininet
    sudo mn --topo linear,3
    
### Step 2: Test Connectivity
    pingall

### Step 3: Measure RTT (Delay)
  h1->h2
  h1 ping -c 5 h2
  h1->h3
  h1 ping -c 5 h3


### Step 4: Introduce Artificial Delay
    sudo mn --topo linear,3 --link tc,delay=10ms
    h1 ping -c 5 h3

---

## Results :

1.Network Connectivity Test using pingall
<img width="747" height="618" alt="SS1" src="https://github.com/user-attachments/assets/8b9db9a7-fd21-4128-ab90-5016b1f82b62" />


2.RTT Measurement between Host h1 and Host h2
<img width="753" height="282" alt="SS2" src="https://github.com/user-attachments/assets/2097ff02-9904-4e70-90ed-fdac73378e16" />


3.RTT Measurement between Host h1 and Host h3
<img width="698" height="282" alt="SS3 - Copy" src="https://github.com/user-attachments/assets/a438bfc5-929d-4c1a-b2b1-632b5405af6c" />

4.Comparison of RTT Values Across Different Paths
<img width="703" height="513" alt="SS4" src="https://github.com/user-attachments/assets/02d3a482-0a57-4c9c-927e-49fdc75c45ac" />

5.Delay Variation using Traffic Control (tc)
<img width="1756" height="659" alt="SS5" src="https://github.com/user-attachments/assets/42d7435c-4a3a-412e-843b-0502a9978aee" />

