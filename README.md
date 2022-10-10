# Rocket.Chat Server Setup

This is a custom [rocket.chat](https://docs.rocket.chat/) setup using Docker & docker-compose, adapted from

- <https://docs.rocket.chat/quick-start/deploying-rocket.chat/rapid-deployment-methods/docker-and-docker-compose>
- <https://github.com/frdmn/docker-rocketchat>

## Features

- Instead of [Traefik](https://github.com/traefik/traefik), this setup uses NGIИX, via [nginx-proxy/nginx-proxy](https://github.com/nginx-proxy/nginx-proxy) and [nginx-proxy/acme-companion](https://github.com/nginx-proxy/acme-companion).
- Volume backups via [docker-volume-backup](https://github.com/offen/docker-volume-backup)

## Instructions

1. Clone repo
2. Create a `.env` file based on the example `.env.sample` file and update environment variables accordingly
3. Configure nginx-proxy and nginx-proxy/acme-companion (TODO: provide detailed docs)
4. Setup your backups -- choose any S3-compatible storage, and configure healthchecks.io (TODO: provide detailed docs)
5. Persistence

   ```bash
   mkdir -p data/rocketchat-db-data
   mkdir -p data/rocketchat-media-data
   sudo chown -R 1001 data
   ```
