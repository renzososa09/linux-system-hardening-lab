# Linux System Hardening Lab

## Overview
This project demonstrates how to harden an Ubuntu Linux system to improve security and reduce the attack surface.

The lab was built in a VirtualBox environment and focuses on implementing firewall rules, auditing services, and configuring security protections.

## Lab Environment
Hypervisor: VirtualBox
Operating System: Ubuntu
Host RAM: 16GB

## Security Tools Used
UFW (Uncomplicated Firewall)
Fail2Ban
systemctl
ss (socket statistics)

## Hardening Steps Performed

### 1. Firewall Configuration
Configured UFW to block incoming connections by default.

Commands used:

sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status verbose


### 2. Service Auditing
Checked enabled services and disabled unnecessary services to reduce attack surface.

Command:

systemctl list-unit-files --type=service --state=enabled

Disabled printing services (not needed for server environments):

sudo systemctl disable cups
sudo systemctl disable cups.path
sudo systemctl disable cups.socket


### 3. Brute Force Protection
Installed Fail2Ban to protect against SSH brute-force attacks.

sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban


### 4. Port Auditing
Checked open network ports.

sudo ss -tulnp


## Security Concepts Demonstrated

• Attack surface reduction  
• Firewall policy enforcement  
• Service auditing  
• Brute-force attack mitigation  
• Linux system hardening  

## Future Improvements

• SSH hardening  
• Log monitoring  
• Intrusion detection integration  
• SIEM integration
