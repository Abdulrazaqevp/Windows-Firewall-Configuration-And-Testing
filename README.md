# Firewall Configuration & Testing Project

## Overview
This repository documents the firewall configuration tasks performed to secure a system by managing inbound and outbound network traffic. The project demonstrates rule creation, testing, and verification on both Linux (UFW) and Windows Firewall.linux is optional you can everything on windows


## Tools Used
- Windows Firewall (GUI and PowerShell)
- UFW (Linux command-line firewall)

## Steps Performed

1. **Open Firewall Configuration Tool**  
   - Windows: Firewall with Advanced Security  
   - Linux: UFW terminal  

2. **List Current Firewall Rules**  
   - Linux:
     ```bash
     sudo ufw status numbered
     ```  
   - Windows:
     ```powershell
     Get-NetFirewallRule
     ```

3. **Block Inbound Traffic (Example: Telnet Port 23)**  
   - Linux:
     ```bash
     sudo ufw deny 23
     ```  
   - Windows:
     ```powershell
     New-NetFirewallRule -DisplayName "Block Telnet" -Direction Inbound -LocalPort 23 -Protocol TCP -Action Block
     

4. **Allow Essential Traffic (Example: SSH Port 22)**  
   - Linux:
     ```bash
     sudo ufw allow 22
     ```  
   - Windows:
     ```powershell
     New-NetFirewallRule -DisplayName "Allow SSH" -Direction Inbound -LocalPort 22 -Protocol TCP -Action Allow
     ```

5. **Test Rules**  
   - Verified that blocked ports cannot be accessed.  
   - Verified that allowed ports remain accessible.

---

## Screenshots
All screenshots of command outputs and rule testing are included in the `Firewall Configuration & Testing Report.pdf`

---

## Outcome
- Successfully blocked unnecessary ports (Telnet).  
- Allowed essential services (SSH) while securing the system.  
- Verified firewall rule effectiveness.

---

## Scripts
- `scripts/block_telnet.sh`: UFW command to block Telnet  
- `scripts/allow_ssh.sh`: UFW command to allow SSH
