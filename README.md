# Linux System Hardening Lab

## Overview
This project demonstrates how to harden an Ubuntu Linux system to improve security and reduce the attack surface.

The lab was built in a VirtualBox environment and focuses on implementing firewall rules, auditing services, and configuring security protections.

## Lab Environment
```bash
Hypervisor: VirtualBox
Operating System: Ubuntu
Host RAM: 16GB
```

## Security Tools Used
## Firewall Configuration

Configured UFW to block incoming connections by default.

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status verbose
```

![UFW Status](ufw-status.png)

---

## Service Auditing

Checked enabled services and audited running services to identify unnecessary services.

```bash
systemctl list-unit-files --type=service --state=enabled
```

![Service Audit](service-audit.png)

---

## Disabled Unnecessary Services

Disabled the CUPS printing service to reduce attack surface since it is not required for this system.

```bash
systemctl status cups
```

![CUPS Disabled](cups-disabled.png)

---

## Brute Force Protection

Installed and enabled Fail2Ban to mitigate SSH brute-force attacks.

```bash
sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
sudo systemctl status fail2ban
```

![Fail2Ban Status](fail2ban-status.png)

---

## Open Port Audit

Audited listening network ports to verify only necessary services were exposed.

```bash
sudo ss -tulnp
```

![Open Ports](open-port.png)

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
