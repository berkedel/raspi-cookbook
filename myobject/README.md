# Setup Personal Object Storage Using MinIO

## Stack

- Object storage: [MinIO](https://github.com/minio/minio)
- Reverse Proxy with HTTPS: [Caddy](https://github.com/caddyserver/caddy) and [Cloudflare module](https://github.com/caddy-dns/cloudflare)

## Prerequisites

- Created cloudflare API Tokens from your profile using `Edit zone DNS` template. Refer [here](https://support.cloudflare.com/hc/en-us/articles/200167836-Managing-API-Tokens-and-Keys)

## Update Config

1. Replace [<CLOUDFLARE_API_TOKENS>](./caddy/Caddyfile#L3) with your cloudflare API token.
1. Change your secrets in [dotenv](./dotenv)

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
