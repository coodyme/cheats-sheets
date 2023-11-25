https://www.youtube.com/watch?v=ZtqBQ68cfJc

# General Commands

```bash
grep -rnw '/path' -e 'pattern'

# Example: Search 'CRETE TABLE rle' in '/home/augusto/projects'
sudo grep -rnw '/home/augusto/projects' -e 'CREATE TABLE rle'
```

```bash
which code
```

# RSYNC

```bash
# Copy files via ssh
rsync -avz -e 'ssh' /path/to/local/dir user@remotehost:/path/to/remote/dir
```

# System

```bash
# Shutdown 
sudo shutdown -h now
```

# System Manager

```bash
# List all Connections
ss

# Summary Statistics
ss -S

# IPv4 and IPv6 Socket Connections
ss -4

# Manual
man ss
```

# Rename

```bash
sudo apt-get install rename
```

```bash
rename 's/name/newName/' *.py
```

```bash
rename 's/\s+/_/g' *
```

```bash
rename 's/\.jpeg/\.jpg/' *.jpeg
```

```bash
# To Upper
rename 'y/a-z/A-Z/' *

# To Lower
rename 'y/A-Z/a-z/' *
```

# Find

```bash
# Find in path . "dir" where type is dir (d) and prune
find . -name "node_modules" -type d -prune | xargs du -hcs
```

```bash
find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
```

# Summarize disk usage (du)

```bash
# Dir size human readable separate dir
du -hcs
```

# Process

```bash

sudo lsof -t -i:"PORT" 

sudo lsof -t -i:5500
```

```bash

sudo kill "PID"

sudo kill 23202
```

```bash
ps aux | grep -i "PROCESS"

ps aux | grep -i zat

# OR

pgrep -w zat
```

# Count lines of code

```jsx
find . -name '*.js' | xargs wc -l
```