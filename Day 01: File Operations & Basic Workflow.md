# Day 01: File Operations & Basic Workflow

## Environment
- Ubuntu Server (CLI only)

“I start by confirming my location using `pwd`, then navigate to the working directory with `cd`. I create or prepare files using `touch` and verify them with `ls -lah`. When testing or logging, I write outputs using `echo`, being careful to use `>>` to append instead of `>` to avoid overwriting important data. Before making any changes, I back up configs using `cp` or rename them with `mv`. If I need to locate files quickly, I use `find` with filters like `*.yaml`. This workflow helps me safely manage files and prevent common mistakes in production environments.”

## CLI Commands
```bash
pwd
mkdir -p ~/linux-lab/day1
cd ~/linux-lab/day1
touch app.log notes.txt config.yaml
ls -lah
echo "server started" > app.log
cat app.log
mkdir backups
cp config.yaml backups/
mv notes.txt notes.old.txt
find ~/linux-lab -name "*.yaml"
```

## Key Concepts
- `pwd`, `cd` → always know where you are before making changes
- `touch`, `ls` → create and verify files
- `>` → overwrite file (be careful)
- `cp`, `mv` → backup and rename before modifying configs
- `find` → quickly locate files across directories

## When to Use (Real DC Scenario)
- Creating test logs before deploying or restarting a service
- Backing up config files before making changes
- Renaming old files to avoid accidental overwrite
- Searching for config files during troubleshooting

## Verification Commands
```bash
pwd
ls -lah
cat app.log
find ~/linux-lab -name "*.yaml"
```
