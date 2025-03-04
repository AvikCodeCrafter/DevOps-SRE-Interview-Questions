```md
# Shell Scripts for System Administration

## 1. Monitor Network Connectivity and Log if Unreachable
```bash
#!/bin/bash
SERVER="8.8.8.8"
LOGFILE="/var/log/network_monitor.log"

ping -c 2 $SERVER > /dev/null 2>&1
if [ $? -ne 0 ]; then
    echo "$(date): $SERVER is unreachable" >> $LOGFILE
fi
```

## 2. Check Free Memory and Alert if Below 10%
```bash
#!/bin/bash
THRESHOLD=10
AVAILABLE=$(free | awk '/Mem/{printf("%.0f"), $4/$2 * 100}')
if [ "$AVAILABLE" -lt "$THRESHOLD" ]; then
    echo "Warning: Free memory is below $THRESHOLD%!"
fi
```

## 3. Monitor and Restart Stopped Processes
```bash
#!/bin/bash
PROCESSES=("nginx" "mysql")

for process in "${PROCESSES[@]}"; do
    if ! pgrep -x "$process" > /dev/null; then
        echo "Restarting $process..."
        systemctl restart "$process"
    fi
done
```

## 4. Download Latest Backup File from Remote Server
```bash
#!/bin/bash
REMOTE_SERVER="user@remote-server.com"
REMOTE_DIR="/backups"
LOCAL_DIR="/local_backups"
LOGFILE="/var/log/backup_download.log"

LATEST_FILE=$(ssh $REMOTE_SERVER "ls -t $REMOTE_DIR | head -n1")
scp "$REMOTE_SERVER:$REMOTE_DIR/$LATEST_FILE" "$LOCAL_DIR/"
echo "$(date): Downloaded $LATEST_FILE" >> $LOGFILE
```

## 5. Create New User with Specific Permissions
```bash
#!/bin/bash
USERNAME="newuser"
HOME_DIR="/home/$USERNAME"

useradd -m -d "$HOME_DIR" -s /bin/bash "$USERNAME"
chmod 700 "$HOME_DIR"
passwd "$USERNAME"
echo "User $USERNAME created successfully!"
```

## 6. Find Large Files and Move Them
```bash
#!/bin/bash
SOURCE_DIR="/path/to/source"
DEST_DIR="/path/to/destination"

find "$SOURCE_DIR" -type f -size +1G -exec mv {} "$DEST_DIR" \;
```

## 7. Check Uptime and Log if Less than 24 Hours
```bash
#!/bin/bash
LOGFILE="/var/log/uptime_check.log"

UPTIME_HOURS=$(awk '{print int($1/3600)}' /proc/uptime)
if [ "$UPTIME_HOURS" -lt 24 ]; then
    echo "$(date): Server restarted, uptime is $UPTIME_HOURS hours." >> $LOGFILE
fi
```

## 8. Check Disk Space on Multiple Servers
```bash
#!/bin/bash
SERVERS=("server1" "server2")
THRESHOLD=90

for SERVER in "${SERVERS[@]}"; do
    USAGE=$(ssh "$SERVER" "df -h / | awk 'NR==2 {print \$5}' | sed 's/%//'")
    if [ "$USAGE" -gt "$THRESHOLD" ]; then
        echo "Alert: $SERVER disk usage at $USAGE%!"
    fi
done
```

## 9. Fetch and Analyze Logs from Remote Server
```bash
#!/bin/bash
REMOTE_SERVER="user@remote-server.com"
LOG_DIR="/var/log"
LOCAL_DIR="/logs"
ERROR_KEYWORDS="error|failed|critical"

scp "$REMOTE_SERVER:$LOG_DIR/*.log" "$LOCAL_DIR/"
grep -E "$ERROR_KEYWORDS" "$LOCAL_DIR"/*.log
```

## 10. Check Web Application Status and Restart if Down
```bash
#!/bin/bash
SERVICE="nginx"
URL="http://yourwebsite.com"

if ! curl -s --head "$URL" | grep "200 OK" > /dev/null; then
    echo "Web application down! Restarting $SERVICE..."
    systemctl restart "$SERVICE"
fi
```

## 11. Count Lines in `.log` Files
```bash
#!/bin/bash
LOG_DIR="/var/log"
find "$LOG_DIR" -type f -name "*.log" -exec wc -l {} +
```

## 12. Compare Two Directories
```bash
#!/bin/bash
diff -rq /path/to/dir1 /path/to/dir2
```

## 13. Remove Old Logs (Older Than 7 Days)
```bash
#!/bin/bash
LOG_DIR="/var/log"
find "$LOG_DIR" -type f -mtime +7 -exec rm {} \;
```

## 14. Report Active Logged-in Users
```bash
#!/bin/bash
who > /var/log/active_users_report.log
```

## 15. Monitor Log File Sizes and Alert if Exceeding Limit
```bash
#!/bin/bash
LOG_DIR="/var/log"
THRESHOLD_MB=500

find "$LOG_DIR" -type f -name "*.log" -size "+$THRESHOLD_MB"M -exec echo "Large log file: {}" \;
```

## 16. Update System and Reboot if Needed
```bash
#!/bin/bash
apt update && apt upgrade -y
if [ -f /var/run/reboot-required ]; then
    reboot
fi
```

## 17. Rotate and Compress Logs
```bash
#!/bin/bash
LOG_DIR="/var/log"
BACKUP_DIR="/var/log/backup"

mkdir -p "$BACKUP_DIR"
find "$LOG_DIR" -type f -name "*.log" -mtime +1 -exec gzip {} \;
mv "$LOG_DIR"/*.gz "$BACKUP_DIR/"
```

## 18. Validate File Integrity with Checksums
```bash
#!/bin/bash
DIR="/path/to/files"

find "$DIR" -type f -exec md5sum {} + > checksums.md5
md5sum -c checksums.md5
```

## 19. Check and Install Missing Software
```bash
#!/bin/bash
SOFTWARES=("docker" "git")

for SOFTWARE in "${SOFTWARES[@]}"; do
    if ! command -v "$SOFTWARE" &> /dev/null; then
        echo "Installing $SOFTWARE..."
        apt install -y "$SOFTWARE"
    fi
done
```

## 20. Automate SSL Certificate Creation
```bash
#!/bin/bash
DOMAIN="yourdomain.com"
EMAIL="admin@yourdomain.com"

apt install certbot -y
certbot certonly --standalone -d "$DOMAIN" --email "$EMAIL" --agree-tos --non-interactive
```
```

