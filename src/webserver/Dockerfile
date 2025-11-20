FROM caddy:2.10.2-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/hslatman/caddy-crowdsec-bouncer/http \
    --with github.com/lucaslorentz/caddy-docker-proxy/v2

FROM caddy:2.10-alpine

COPY defaultpage.html /static/defaultpage.html
COPY Caddyfile /etc/caddy/Caddyfile

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
