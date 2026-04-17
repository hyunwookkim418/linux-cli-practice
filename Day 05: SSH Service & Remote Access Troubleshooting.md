# Day 05: SSH Service & Remote Access Troubleshooting

30-Second Summary: When SSH access fails, I follow a structured approach:
First, I verify network connectivity, then confirm the SSH service is running and listening on port 22, and finally check firewall rules.
This ensures I quickly isolate whether the issue is network, service, or security-related.

---

## Environment
- Ubuntu Server (CLI only)

---

## CLI Commands

```bash
pwd
hostname
ip a
ping -c 4 8.8.8.8
ss -tulpen | grep ssh
systemctl status ssh
sudo systemctl restart ssh
sudo systemctl enable ssh
sudo journalctl -u ssh -n 30 --no-pager
sudo ufw status verbose
```

---

## Key Concepts (Practical Explanation)
- `ss -tulpen | grep ssh`
  Checks if the SSH service is actively listening on port 22.
  If nothing shows → SSH is NOT accepting connections (service down or misconfigured).
  If you see `:22` → service is ready at the network level.

- `systemctl status ssh`
  Shows the real state of the SSH service (running, failed, inactive).
  Also displays recent logs → useful for quick failure hints without digging deeper.

- `journalctl -u ssh`
  Pulls detailed logs for SSH (startup errors, auth failures, config issues).
  This is your **go-to command when “it should work but doesn’t.”**

- `ufw status verbose`
  Confirms whether firewall rules allow or block SSH (port 22).
  Even if SSH is running, firewall can silently block access.

- `Troubleshooting Order (Critical Habit)`
  Always follow:
  1. Network (IP / ping)
  2. Service (SSH running?)
  3. Port (listening?)
  4. Firewall (allowed?)
---

## Verification Commands

```bash
systemctl is-active ssh
ss -tulpen | grep :22
sudo ufw status
ip a
```
