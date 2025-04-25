# `beszel`

## server setup

- use the `beszel-server` service first (for the initial setup `beszel-agent` is not needed)
- login with `email` and `password`
- enable `GitHub` OAuth using `client_id` and `client_secret`
- logout and logback in with OAuth

## agent setup

- then in the webui, `Add New System`
- copy the `Port` and `Public Key`
- fill in the .env file's `AGENT_PORT` and `AGENT_SSH_KEY`
- add some arbitary `Name` like "homelab-beszel-agent"
- for `Host/IP` use the `beszel-agent` docker compose service name (no IP as agent has the same IP as server, if different then IP)
- make sure the `beszel-agent` compose service is running after this.
