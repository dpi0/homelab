# `traefik`

## tailscale

- wasn't able to properly deploy tailscale-docker + traefik + cloudflare
- went with tailscale (host) + traefik
- `sudo tailscale up` and connect the homelab machine via provided url
- create DNS entry for homelab machine in cloudflare
- add in the extra labels for each container with the `FQDN_TAILSCALE` variable
