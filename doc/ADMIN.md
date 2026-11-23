## Configuration

The configuration file is at `__INSTALL_DIR__/conf/mtg.toml`. Key settings:

- `secret` — The MTProto secret. Changing this requires restarting the service.
- `bind-to` — The IP and port the proxy listens on.
- `[network] dns` — The DNS resolver used for IP resolution.
- `[stats.prometheus]` — Enable/disable the Prometheus metrics endpoint.

After editing the config file, restart the service:
```bash
sudo systemctl restart __APP__
```

## Getting the connection link for Telegram

Generate ready-to-use `tg://proxy` / `https://t.me/proxy` links and QR code URLs directly with:
```bash
sudo __INSTALL_DIR__/mtg access __INSTALL_DIR__/conf/mtg.toml
```

Or inspect your raw configuration file:
```bash
sudo cat __INSTALL_DIR__/conf/mtg.toml
```

Use the generated link or configure the `secret` and your server's public IP + port (`__PORT__`) manually in Telegram:
**Settings → Data and Storage → Proxy Settings → Add Proxy → MTProto**
