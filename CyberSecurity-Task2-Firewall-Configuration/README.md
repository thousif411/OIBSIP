# Task 2 - Basic Firewall Configuration with UFW

## Objective
Configure and manage a basic firewall using UFW (Uncomplicated Firewall) on Kali Linux.

## Tools Used
- Kali Linux
- UFW (Uncomplicated Firewall)
- Terminal

## Steps Performed
1. Installed UFW.
2. Verified the installation.
3. Checked firewall status.
4. Enabled the firewall.
5. Allowed SSH on port 22.
6. Blocked Telnet on port 23.
7. Verified firewall rules.
8. Deleted the Telnet rule.
9. Verified the final firewall configuration.

## Commands Used

```bash
sudo apt update
sudo apt install ufw -y
ufw --version
sudo ufw status
sudo ufw enable
sudo ufw status verbose
sudo ufw allow 22/tcp
sudo ufw deny 23/tcp
sudo ufw status numbered
sudo ufw delete 2
sudo ufw delete 3
```

## Outcome

Successfully configured and managed firewall rules using UFW while learning how firewalls control network traffic and improve system security.
