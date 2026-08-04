# MetaCubeXD for fnOS

Mihomo Dashboard — manage rules, nodes, and connections. Connects directly to local Mihomo API.

[![GitHub release](https://img.shields.io/github/v/release/techysy/metacubexd-fnos?label=Release&color=blue)](https://github.com/techysy/metacubexd-fnos/releases)
[![Downloads](https://img.shields.io/github/downloads/techysy/metacubexd-fnos/total?label=Downloads&color=green)](https://github.com/techysy/metacubexd-fnos/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/techysy/metacubexd-fnos/blob/main/LICENSE)
[![fnOS 1.1.31xx](https://img.shields.io/badge/fnOS-1.1.31xx+-orange.svg)](https://developer.fnnas.com/docs/guide)
[![MetaCubeXD v1.271.0](https://img.shields.io/badge/MetaCubeXD-v1.271.0-purple.svg)](https://github.com/metacubex/metacubexd)

> Packages [MetaCubeXD](https://github.com/metacubex/metacubexd) as a fnOS desktop window app.

- [中文 README](./README.md)

---

## ✨ Features

- 🖥️ **Mihomo dashboard** — manage rules, nodes, connections
- 🔗 **Direct local Mihomo API** — no extra service needed
- 📦 **One-click deploy** — App Center manual install

## 🚀 Quick Install

1. Download `metacubexd-x.x.x.fpk` from [Releases](https://github.com/techysy/metacubexd-fnos/releases)
2. fnOS **App Center → Manual Install** → select the fpk
3. Click the **MetaCubeXD** icon (port 9091)
4. The panel auto-connects to Mihomo API (default `http://192.168.31.31:9090`)

## 📖 Usage

### App Settings

Configure the Mihomo API address in **App Center → App Settings** (no code changes needed):

| Setting | Default | Description |
|---------|---------|-------------|
| Mihomo API address | `http://192.168.31.31:9090` | Mihomo external-controller address |

**Restart** the app to apply (App Center → Stop → Start).

### Ports

| Service | Port |
|---------|------|
| Dashboard | 9091 |
| Mihomo API | 9090 |
| Mihomo HTTP proxy | 7890 |

## ⚠️ Remote Access Note (Mixed Content)

Opening via **fnOS remote access (`https://<app>.techysy.fnos.net` / FN Connect)** loads the page over **HTTPS** while Mihomo is **HTTP** — the browser blocks the request as **mixed content**, showing "Connection blocked".

**Working options**:

1. **LAN direct**: open `http://192.168.31.101:9091` in a browser (HTTP page to HTTP backend, no mixed content)
2. **fnOS desktop Chrome** (fygo-browser): open `http://127.0.0.1:9091` on the NAS itself — fully bypasses the issue
3. **Public HTTPS**: reverse-proxy Mihomo to a public HTTPS address (costly)

> Detailed troubleshooting: [TROUBLESHOOTING.md](./TROUBLESHOOTING.md)

## 🐛 Troubleshooting

Install/connect/mixed-content issues: see [TROUBLESHOOTING.md](./TROUBLESHOOTING.md).

## 🛠️ Build from Source

```bash
# On the fnOS NAS
fnpack build   # produces metacubexd.fpk
```

## 🔮 Roadmap

Repack when upstream [metacubex/metacubexd](https://github.com/metacubex/metacubexd) releases a new version:

- Track upstream updates
- New node type/protocol support
- Dashboard UI/UX improvements

## 📚 Related

- [metacubex/metacubexd](https://github.com/metacubex/metacubexd) — upstream · [live demo](https://metacubex.github.io/metacubexd/)
- [Hermes WebUI](https://github.com/techysy/hermes-webui-fnos) · [9Router](https://github.com/techysy/9router-fnos) · [Strava Panel](https://github.com/techysy/strava-panel-fnos) — more fnOS apps
- [fnOS Developer Docs](https://developer.fnnas.com/docs/guide)

## License

MIT — same as [metacubex/metacubexd](https://github.com/metacubex/metacubexd)
