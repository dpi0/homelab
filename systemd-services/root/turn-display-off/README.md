## turn-display-off

```bash
sudo ln -sf $HOME/homelab/systemd-services/root/turn-display-off/turn-display-off.service /etc/systemd/system/

sudo systemctl daemon-reload

sudo systemctl enable turn-display-off.service

sudo systemctl status turn-display-off.service

systemctl list-timers --all | grep turn-display-off
```
