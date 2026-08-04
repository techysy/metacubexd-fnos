# MetaCubeXD for fnOS

Mihomo Dashboard — 代理面板，管理规则、节点、连接，支持直连内网 Mihomo API。

[![GitHub release](https://img.shields.io/github/v/release/techysy/metacubexd-fnos?label=Release&color=blue)](https://github.com/techysy/metacubexd-fnos/releases)
[![Downloads](https://img.shields.io/github/downloads/techysy/metacubexd-fnos/total?label=Downloads&color=green)](https://github.com/techysy/metacubexd-fnos/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/techysy/metacubexd-fnos/blob/main/LICENSE)
[![fnOS 1.1.31xx](https://img.shields.io/badge/fnOS-1.1.31xx+-orange.svg)](https://developer.fnnas.com/docs/guide)
[![MetaCubeXD](https://img.shields.io/github/v/release/metacubex/metacubexd?label=MetaCubeXD&color=purple)](https://github.com/metacubex/metacubexd)

> 将 [MetaCubeXD](https://github.com/metacubex/metacubexd) 打包为飞牛 NAS (fnOS) 桌面窗口应用。

- [English README](./README.en.md)

---

## ✨ 功能亮点

- 🖥️ **Mihomo 代理面板** — 管理规则、节点、连接
- 🔗 **直连内网 Mihomo API** — 无需额外服务
- 📦 **一键部署** — App Center 手动安装即用

## 🚀 快速安装

1. 从 [Releases](https://github.com/techysy/metacubexd-fnos/releases) 下载 `metacubexd-x.x.x.fpk`
2. 飞牛 **App Center → 手动安装** → 选择 fpk
3. 桌面出现 **MetaCubeXD** 图标，点击打开面板（端口 9091）
4. 面板自动连接 Mihomo API（默认 `http://192.168.31.31:9090`）

## 📖 使用说明

### 应用设置

安装后可在 **App Center → 应用设置** 配置 Mihomo API 地址，无需改代码：

| 设置项 | 默认值 | 说明 |
|---|---|---|
| Mihomo API 地址 | `http://192.168.31.31:9090` | Mihomo 的 external-controller 地址 |

修改后需**重启应用**生效（App Center → 停止 → 启动）。

### 端口

| 服务 | 端口 |
|---|---|
| 面板 | 9091 |
| Mihomo API | 9090 |
| Mihomo HTTP 代理 | 7890 |

## ⚠️ 远程访问注意事项（混合内容）

通过 **fnOS 远程访问（`https://<app>.techysy.fnos.net` / FN Connect）** 打开面板时，页面以 **HTTPS** 加载而 Mihomo 后端是 **HTTP**，浏览器会因**混合内容**拦截请求，面板报"连接被阻止"。

**可行方案**：

1. **局域网直连**：浏览器访问 `http://192.168.31.101:9091`（HTTP 加载连 HTTP 后端，无混合内容）
2. **fnOS 桌面 Chrome**（fygo-browser）：飞牛本机打开 `http://127.0.0.1:9091`，浏览器跑在 NAS 上，完全绕过
3. **暴露公网 HTTPS**：把 Mihomo 反向代理成公网 HTTPS 地址（成本较高）

> 详细排查记录见 [TROUBLESHOOTING.md](./TROUBLESHOOTING.md)

## 🐛 问题排查

安装/连接/混合内容等问题的详细排查记录，见 [TROUBLESHOOTING.md](./TROUBLESHOOTING.md)。

## 🛠️ 从源码构建

```bash
# 在飞牛上
fnpack build   # 生成 metacubexd.fpk
```

## 🔮 迭代计划

等待上游 [metacubex/metacubexd](https://github.com/metacubex/metacubexd) 发布新版本后重新打包：

- 跟进上游版本更新
- 新增节点类型/协议支持
- 面板 UI/UX 优化

## 📚 相关项目

- [metacubex/metacubexd](https://github.com/metacubex/metacubexd) — 上游开源项目 · [在线 Demo](https://metacubex.github.io/metacubexd/)
- [Hermes WebUI](https://github.com/techysy/hermes-webui-fnos) · [9Router](https://github.com/techysy/9router-fnos) · [Strava Panel](https://github.com/techysy/strava-panel-fnos) — 更多 fnOS 应用
- [fnOS 开发者文档](https://developer.fnnas.com/docs/guide)

## License

MIT — 与 [metacubex/metacubexd](https://github.com/metacubex/metacubexd) 一致
