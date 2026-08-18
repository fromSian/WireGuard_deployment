WireGuard VPN deployment for an Ubuntu Droplet using Docker Compose.

## 1. firewall

Allow inbound:

- UDP 51820 from anywhere
- TCP 22 only from your own IP if possible

Keep outbound traffic allowed.

```
docker compose pull
docker compose up -d
```

After startup:

```bash
find config -maxdepth 3 -type f | sort
```

The first peer is normally under:

```text
config/peer1/
```

Import the generated `.conf` file into the WireGuard app.

For a QR code:

```bash
docker exec wireguard /app/show-peer 1
```

```bash
docker compose ps
docker logs wireguard --tail 100
```
