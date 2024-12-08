# Use the Alpine builder image for Caddy
FROM caddy:builder AS builder

# Build the custom Caddy binary with the duckdns module
RUN xcaddy build \
    --with github.com/caddy-dns/duckdns

# Use the Alpine runtime image for Caddy
FROM caddy:latest

# Copy the custom-built Caddy binary into the runtime image
COPY --from=builder /usr/bin/caddy /usr/bin/caddy
