FROM caddy:2.10-builder-alpine AS builder

# Esta línea ayuda a saltar bloqueos regionales
ENV GOPROXY=https://proxy.golang.org,direct

RUN xcaddy build \
    --with github.com/BadAimWeeb/caddy-uwsgi-transport \
    --with github.com/mholt/caddy-ratelimit

FROM caddy:2.10-alpine AS base
COPY --from=builder /usr/bin/caddy /usr/bin/caddy