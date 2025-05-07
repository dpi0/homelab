## backrest-backup

```bash
sudo ln -sf $HOME/homelab/systemd-services/root/backrest-backup/backrest-backup.service /etc/systemd/system/
sudo ln -sf $HOME/homelab/systemd-services/root/backrest-backup/backrest-backup.timer /etc/systemd/system/

sudo systemctl daemon-reload

sudo systemctl enable --now backrest-backup.timer

sudo systemctl status backrest-backup.service
sudo systemctl status backrest-backup.timer

systemctl list-timers --all | grep backrest-backup
```
