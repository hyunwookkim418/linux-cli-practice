# Day 03: File Operations and Search

## Environment
- Ubuntu Server (CLI only)

## CLI Commands
```bash
pwd
mkdir -p ~/linux-lab/day3
cd ~/linux-lab/day3
touch app.log notes.txt config.yaml
ls -lah
echo "server started" > app.log
cat app.log
cp config.yaml backups/
mv notes.txt notes.old.txt
find ~/linux-lab -name "*.yaml"
```

## Key Concepts
- `mkdir -p` creates directories safely (no error if already exists).
- `touch` creates empty files quickly.
- `cp` and `mv` are used for backup and renaming in real operations.
- `echo > file` overwrites content (be careful in production).
- `find` is critical for locating configs/logs across large systems.

## When to Use (Real DC Scenario)
- You need to quickly create config files, back them up before changes, and locate YAML/JSON configs across multiple directories during troubleshooting or deployment.

## Verification Commands
```bash
ls -lah ~/linux-lab/day3
cat ~/linux-lab/day3/app.log
find ~/linux-lab -name "*.yaml"
```
