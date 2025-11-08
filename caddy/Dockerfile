# 1. build Caddy
FROM caddy:2-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare


# 2. run Caddy
FROM caddy:2-alpine

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
