## shutdown-daily

```bash
sudo ln -sf $HOME/homelab/systemd-services/root/shutdown-daily/shutdown-daily.service /etc/systemd/system/
sudo ln -sf $HOME/homelab/systemd-services/root/shutdown-daily/shutdown-daily.timer /etc/systemd/system/

sudo systemctl daemon-reload

sudo systemctl enable shutdown-daily.timer

sudo systemctl status shutdown-daily.service
sudo systemctl status shutdown-daily.timer

systemctl list-timers --all | grep shutdown-daily
```
