# Hetzner Web

A lightweight Hetzner traffic console with daily/hourly views, rebuild actions, DNS checks, and a clean dashboard.

## Features

- Real-time server traffic (outbound/inbound)
- Daily/hourly breakdown tables
- DNS check + rebuild actions
- Trend sparkline per server
- Traffic bar chart (outbound/inbound)
- Basic Auth login

## Quick Start (Docker)

```bash
cp config.example.yaml config.yaml
cp web_config.example.json web_config.json
cp report_state.example.json report_state.json
# edit config.yaml + web_config.json

docker compose up -d --build
```

Open: `http://<server-ip>:1227`

## Configuration

### `config.yaml`
- `hetzner.api_token`: Hetzner Cloud API token
- `traffic.limit_gb`: traffic limit (GB)
- `cloudflare.record_map`: server_id -> DNS record
- `rebuild.snapshot_id_map`: server_id -> snapshot_id

### `web_config.json`
- `username` / `password`: Basic Auth credentials
- `tracking_start`: optional, e.g. `2026-01-01 00:00`

## Notes

- Runtime data is stored in `report_state.json` (gitignored).
- `config.yaml` and `web_config.json` are gitignored for safety.

## License

MIT
