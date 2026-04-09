Day 02: Linux Basic Server Health Check

30-Second Summary: When a Linux server is slow or unresponsive, I start with a quick health check: system identity, uptime/load, disk, memory, network, and running processes. This structured approach helps me quickly identify whether the issue is resource-related, network-related, or process-related before diving deeper.

## Environment
- Ubuntu Server (CLI only)

## CLI Commands
```bash
pwd
hostname
whoami
date
uptime
df -h
free -h
ip a
ping -c 4 8.8.8.8
ps aux | head
top
exit
```

## Key Concepts
- Always start with basic system context (who, where, when).
- Check health in order: uptime → disk → memory → network → processes.
- `df -h` → disk space issues (very common in real servers).
- `free -h` → memory pressure.
- `top` → real-time CPU/memory usage by process.

## When to Use (Real DC Scenario)
- Server is slow
- Application is not responding
- Users report intermittent access issues
 
## Verification Commands
```bash
uptime
df -h
free -h
ping -c 2 8.8.8.8
```
