### Package management (dnf)
**Update package repositories:** *sudo dnf check-update*
**Upgrade all system packages:** *sudo dnf upgrade --refresh*
**Install a specific package:** *sudo dnf install [package_name]*
**Remove unused packages:** *sudo dnf autoremove*

### System Service Management
**Reboot system:** *sudo systemctl reboot*
**Power off system:** *sudo systemctl poweroff*
**Start a service:** *sudo systemctl start [service_name]*
**Stop a service:** *sudo systemctl stop [service_name]*
**Check service status:** *sudo systemctl status [service_name]*

### System **Information**
**View Fedora version:** cat /etc/fedora-release
**Full system information:** uname -aCheck 
**disk space:** df -h
**Check system memory:** free -m

### Network Manager
**List wireless networks:** *nmcli device wifi list*
**Connect to Wi-Fi:** *nmcli device wifi connect [SSID] password [password]*
**Check active connections:** *nmcli connection show --active*