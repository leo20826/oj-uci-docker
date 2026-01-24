FROM caddy:2.10-builder-alpine AS builder

# Usamos el proxy chino (muy estable para saltar bloqueos de Google)
# ENV GOPROXY=https://goproxy.cn,direct

RUN xcaddy build \
    --with github.com/BadAimWeeb/caddy-uwsgi-transport \
    --with github.com/mholt/caddy-ratelimit

FROM caddy:2.10-alpine AS base
COPY --from=builder /usr/bin/caddy /usr/bin/caddy
