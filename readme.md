# cloudflocaddy

Caddy container that serves localhost with automatic SSL.

## Configuration

You need to create a `docker-compose.override.yml` file with these environment variables:

```yml
version: '3'
services:
  cloudflocaddy:
    environment:
      CLOUDFLARE_API_KEY: API_KEY
      CLOUDFLARE_EMAIL: CLOUD@FLARE.EMAIL
      DOMAIN: localhost.yourdomain.com
      PORT: 8080
```

You also need to set the DNS for `localhost.yourdomain.com` to `A 127.0.0.1` (alternatively, edit `/etc/hosts`).

This example setup will proxy `https://localhost.yourdomain.com` to `http://127.0.0.1:8080`.

## Running

```sh
# start in foreground
docker-compose up

# start in background
docker-compose up -d
```
