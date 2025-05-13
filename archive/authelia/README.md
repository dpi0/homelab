# `authelia`

## create secret files

<https://www.authelia.com/blog/authelia--traefik-setup-guide/>

```bash
VOLUME=/path/to/volume
mkdir -p $VOLUME/authelia/secrets

sudo chown 8000:8000 $VOLUME/authelia/secrets
sudo chmod 0700 $VOLUME/authelia/secrets

docker run --rm \
  -u 8000:8000 \
  -v $VOLUME/authelia/secrets:/secrets \
  docker.io/authelia/authelia \
  sh -c "cd /secrets && \
    authelia crypto rand --length 64 \
      session_secret.txt \
      storage_encryption_key.txt \
      jwt_secret.txt"
```

## generate user passwords

<https://www.authelia.com/reference/guides/passwords/#passwords>


```bash
# hash with a password prompt
docker run --rm -it authelia/authelia:latest authelia crypto hash generate argon2

# without prompt
docker run --rm authelia/authelia:latest authelia crypto hash generate argon2 --password 'password'
```
