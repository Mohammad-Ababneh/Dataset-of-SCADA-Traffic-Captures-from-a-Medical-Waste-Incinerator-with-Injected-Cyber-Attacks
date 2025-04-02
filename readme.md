# SCADA Traffic Dataset from a Medical Waste Incinerator with Injected Cyber Attacks

This repository contains a dataset of packet capture (PCAP) files from a live SCADA (Supervisory Control and Data Acquisition) system deployed at a medical waste incinerator, including both normal operational traffic and synthetic cyber attack scenarios.

The dataset is designed to support research in the cybersecurity of industrial control systems (ICS), especially for intrusion detection, protocol analysis, and machine learning-based anomaly detection.

## Dataset Overview

- **Duration:** 14 consecutive days of live SCADA traffic capture
- **System:** Siemens S7-1500/ET200MP-based PLC with a Windows 10 HMI
- **Protocols:** PROFINET, OPC (TCP port 102), LLDP
- **Normal Traffic:** 14 PCAP files (`day01.pcap` to `day14.pcap`)
- **Attack-Injected Traffic:** 8 folders, each representing a specific attack with ~20,000 injected packets

---

## Repository Structure

Repository/ ├── Normal_Traffic/ │ ├── day01.pcap │ ├── ... │ └── day14.pcap ├── Attack_Injected_Traffic/ │ ├── mitm/ │ │ └── traffic_with_mitm_attack.pcap │ ├── replay/ │ │ └── traffic_with_replay_attack.pcap │ ├── fuzzing/ │ ├── command_flooding/ │ ├── data_spoofing/ │ ├── s7comm_exploit/ │ ├── stealthy_injection/ │ └── syn_flooding/

yaml
Copy
Edit

---

## Attack Types

Each synthetic attack was injected offline using custom Python scripts built on Scapy 2.5.0. Below is a summary of the included attack types:

| Attack Type             | Description |
|-------------------------|-------------|
| Man-in-the-Middle (MITM) | Injected packets mimicking intercepted communications |
| Replay                  | Replayed valid traffic to test timing-based detection |
| Packet Fuzzing          | Malformed packets crafted to stress protocol parsers |
| Command Flooding        | Bursts of read/write commands to overload the PLC |
| Data Spoofing           | Fake sensor values simulating malicious data injection |
| Protocol Exploitation   | Use of S7comm weaknesses to disrupt normal behavior |
| Stealthy Injection      | Subtle setpoint changes to simulate covert attacks |
| SYN Flooding            | TCP-level DoS attempts on port 102 |

---

## Use Cases

This dataset is ideal for:

- Training and evaluating intrusion detection systems (IDS)
- Behavioral analysis of SCADA systems under attack
- Testing protocol parsers for robustness against malformed inputs
- Feature extraction for supervised and unsupervised ML models

---

## Collection Environment

- **Location:** Jordan University of Science and Technology (32.4797°N, 35.9839°E)
- **HMI Configuration:**
  - OS: Windows 10
  - Capture Tool: Wireshark 4.0.3
- **PLC Details:**
  - Siemens S7-1500/ET200MP
  - Communication over isolated Ethernet (no internet)
- **Capture Duration:** Each .pcap represents 24 hours of traffic
- **Traffic Volume:** ~1.3–1.5 million packets per day

---

## Tools and Scripts

- `Wireshark 4.0.3`: For packet capture
- `Scapy 2.5.0`: For crafting and injecting attack packets
- `Python 3.12`: Programming environment
- Scripts used for attack injection:
  - `script_mitm.py`
  - `script_replay.py`
  - `script_fuzzing.py`
  - `script_command_flooding.py`
  - `script_data_spoofing.py`
  - `script_s7comm_exploit.py`
  - `script_stealthy_command_injection.py`
  - `script_syn_flooding.py`

---

## Accessing the Dataset

- **Repository Name:** *[To be specified]*
- **DOI / Data ID:** *[To be specified]*
- **Direct Download URL:** *[To be specified]*
- **Access Instructions:** *[To be added once the dataset is published]*
- **License:** *[Specify license type, e.g., CC BY 4.0]*

---

## Acknowledgements

This dataset was created by:

- **Basheer Al-Duwairi** – Conceptualization, Methodology, Data Curation  
- **Ahmed Shatnawi** – Software Development, Validation  
- **Ahmad Al-Hammouri** – Writing, Visualization

No external funding was received for this work.

---

## Citation

Please cite the dataset as follows (placeholder until publication):

Al-Duwairi, B., Shatnawi, A., & Al-Hammouri, A. (2025). Dataset of SCADA Traffic Captures from a Medical Waste Incinerator with Injected Cyber Attacks. [Data Repository Name]. [DOI]

yaml
Copy
Edit

---

## Related Work

- Dataset supports the study of cyber threats including:
  - MITM, Replay, Packet Fuzzing
  - Command Flooding, Data Spoofing
  - S7comm Protocol Exploits
  - Stealthy Injection, SYN Flooding

---

## Limitations

- Focused on Siemens S7-1500; may not generalize to all SCADA systems
- Captures only the HMI-to-PLC link; no visibility into external segments
- Attack injection performed offline; does not reflect timing jitter of live attacks

---

## Contact

For questions or collaborations, contact:

**Basheer Al-Duwairi**  
Department of Network Engineering & Security  
Jordan University of Science and Technology  
Email: `basheer@just.edu.jo`
