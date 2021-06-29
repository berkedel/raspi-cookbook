# Setup Personal Cloud using Nextcloud

## Stack

- Cloud app: [Nextcloud](https://github.com/nextcloud/server)
- PHP FastCGI: [PHP-FPM](https://github.com/php/php-src/tree/master/sapi/fpm)
- Database: [PostgreSQL](https://github.com/postgres/postgres)
- Cache: [Redis](https://github.com/redis/redis)
- Reverse Proxy with HTTPS: [Caddy](https://github.com/caddyserver/caddy) and [Cloudflare module](https://github.com/caddy-dns/cloudflare)

## Prerequisites

- Created cloudflare API Tokens from your profile using `Edit zone DNS` template. Refer [here](https://support.cloudflare.com/hc/en-us/articles/200167836-Managing-API-Tokens-and-Keys)
- Created cloudflare page rule to disable `Rocket Loader` when loading nextcloud with your domain name. Refer [here](https://support.cloudflare.com/hc/en-us/articles/218411427)

## Update Config

1. Replace [<CLOUDFLARE_API_TOKENS>](./caddy/Caddyfile#L3) with your cloudflare API token.
2. Update [NEXTCLOUD_TRUSTED_DOMAINS](./dotenv#L8) and replace [caddy domain config](./caddy/Caddyfile#L1) with your domain.
3. Change the database credential in [dotenv](./dotenv) file

## Installation

To run

```sh
docker-compose build
docker-compose up -d
```

To stop

```sh
docker-compose stop
```
