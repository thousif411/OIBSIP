# Task 1 - Basic Network Scanning with Nmap

## Objective
Perform a basic network scan using Nmap to identify open ports, running services, and the operating system of a local machine.

## Tools Used
- Kali Linux
- Nmap
- VirtualBox

## Target
- IP Address: 192.168.56.104

## Commands Used

### Basic Scan
```bash
nmap 192.168.56.104
```

### Service Version Scan
```bash
nmap -sV 192.168.56.104
```

### OS Detection Scan
```bash
sudo nmap -O 192.168.56.104
```

## Findings
- Host is reachable.
- Port 22 (SSH) is open.
- SSH Service: OpenSSH 10.3p1 Debian 5.
- Operating System detected as Linux.

## Security Analysis
- SSH is used for secure remote administration.
- Only one port is open, reducing the attack surface.
- Strong passwords or SSH keys should be used to secure SSH access.

## Ethical Note
This scan was performed only on my own Kali Linux virtual machine for educational purposes.
