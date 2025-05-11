## immich-hdd-backup

```bash
# /hdd/Media/Immich is owned by root, so sudo required to run script

# sudo mkdir -p /opt/scripts
# sudo cp /home/dpi0/scripts/immich/immich-hdd-backup.sh /opt/scripts/
# sudo chmod 755 /opt/scripts/immich-hdd-backup.sh

sudo ln -sf $HOME/homelab/systemd-services/root/immich-hdd-backup/immich-hdd-backup.service /etc/systemd/system/
sudo ln -sf $HOME/homelab/systemd-services/root/immich-hdd-backup/immich-hdd-backup.timer /etc/systemd/system/

sudo systemctl daemon-reload

sudo systemctl enable --now immich-hdd-backup.timer
sudo systemctl status immich-hdd-backup.timer
```
