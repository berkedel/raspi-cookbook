FROM caddy:2.4.3-builder-alpine AS builder

RUN xcaddy build v2.4.3 --with github.com/caddy-dns/cloudflare@latest

FROM caddy:2.4.3-alpine

COPY --from=builder /usr/bin/caddy /usr/bin/caddy