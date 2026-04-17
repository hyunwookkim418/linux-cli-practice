# Day 06: Disk Usage and Space Troubleshooting

30-Second Summary: “I verified sudo access by running sudo -l. Since it prompted for a password and successfully displayed my permissions, I confirmed that the password was correct and the account had full sudo privileges. The output showed (ALL : ALL) ALL, meaning I can execute any command as root. In Linux, if sudo -l returns results instead of an error, it proves both authentication and authorization are working. From a troubleshooting perspective, this tells me the issue is not permission-related but likely something else.”

## Environment
- Ubuntu Server (CLI only)

## CLI Commands
```bash
pwd
hostname
df -h
df -i
du -sh /var/log
du -xh / | sort -h | tail -20
find /var/log -type f -size +100M
sudo journalctl --disk-usage
sudo journalctl --vacuum-time=7d
sudo find /tmp -type f -mtime +3 -delete
ls -lh /var/log
```

## Key Concepts
- `df -h` checks overall filesystem usage quickly.
- `df -i` checks inode usage, which can also cause “disk full” symptoms.
- `du` helps find which directory is actually consuming space.
- Large log files under `/var/log` are a common cause of sudden disk issues.
- `journalctl --vacuum-time` helps clean old systemd logs safely.

## When to Use (Real DC Scenario)
- A Linux server suddenly becomes slow, patching fails, logs stop writing, or an application crashes because the root filesystem is full.

## Verification Commands
```bash
df -h
df -i
du -sh /var/log
sudo journalctl --disk-usage
```
