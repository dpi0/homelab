# `forgejo`

## simple sqlite setup

- set the SSH port in the setup to be `XX`
- make sure `forgejo` has port mapping `XX:22`
- open port `XX` in firewall `sudo ufw allow XX/tcp`
- in forgejo settings ⇒ ssh/gpg keys, add `forgejo-homelab.pub`


## to push an existing repo to forgejo via SSH/HTTPS

### SSH

#### on client

- create SSH key: `ssh-keygen -t ed25519 -f $HOME/.ssh/forgejo-homelab -C "Forgejo SSH Homelab"`
- copy public key: `cat $HOME/.ssh/forgejo-homelab.pub | wl-copy`
- add this key to <https://git.homelab.bob.tech/user/settings/keys>
- for future shell sessions: `eval "$(ssh-agent -s)"; ssh-add $HOME/.ssh/forgejo-homelab`
- test connection: `ssh -T -p PORT -i $HOME/.ssh/forgejo-homelab git@FORGEJO_HOMELAB_ADDRESS`
- `ssh -T -p 3333 -i $HOME/.ssh/forgejo-homelab git@git.homelab.bob.tech`

<https://forgejo.org/docs/v1.19/user/push-to-create/#using-push-to-create>

```bash
# add new remote "forgejo"
git remote add forgejo "[git@git.homelab.bob.tech:3333]:FORGEJO_USERNAME/CURRENT_REPO_NAME.git"

# verify remote
git remote -v

# make sure to have FORGEJO__repository__ENABLE_PUSH_CREATE_USER=true in compose env
# refer https://codeberg.org/forgejo/forgejo/src/branch/forgejo/custom/conf/app.example.ini
git push forgejo BRANCH_NAME --force
```

### HTTPS

```bash
# add new remote "forgejo"
git remote add forgejo "https://git.homelab.bob.tech/FORGEJO_USERNAME/CURRENT_REPO_NAME.git"

# verify remote
git remote -v

# make sure to have FORGEJO__repository__ENABLE_PUSH_CREATE_USER=true in compose env
git push forgejo BRANCH_NAME --force
# enter FORGEJO_USERNAME
# enter FORGEJO_PASSWORD
```
