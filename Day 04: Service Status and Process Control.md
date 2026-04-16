# Day 04: Service Status and Process Control

## Environment
- Ubuntu Server (CLI only)

## CLI Commands
```bash
pwd
hostname
systemctl status ssh
systemctl list-units --type=service --state=running
ps -ef | head
ps -ef | grep ssh
top
journalctl -xe | tail -20
sudo systemctl restart ssh
ss -tulnp
```

## Key Concepts
- `systemctl` is the main command to check and control services on Ubuntu.
- `ps` shows processes, while top helps you watch live CPU and memory usage.
- `journalctl` is where you check service and system logs when something fails.
- Restarting a service is easy, but you should check status and logs first.
- `ss -tulnp` helps confirm which ports are listening and which process owns them.

## When to Use (Real DC Scenario)
- A server is reachable by ping, but SSH is not working.
- An application team says “the service is down.”
- A Linux server feels slow, and you need to see whether a process is consuming resources.

## Verification Commands
```bash
systemctl status ssh
ps -ef | grep ssh
ss -tulnp | grep :22
journalctl -u ssh --no-pager | tail -20
```

