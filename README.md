# MetaCubeXD fnOS App

[![GitHub release](https://img.shields.io/github/v/release/techysy/metacubexd-fnos?label=Latest&color=blue)](https://github.com/techysy/metacubexd-fnos/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/techysy/metacubexd-fnos/blob/main/LICENSE)
[![fnOS 1.1.31xx](https://img.shields.io/badge/fnOS-1.1.31xx+-orange.svg)](https://developer.fnnas.com/docs/guide)
[![MetaCubeXD v1.271.0](https://img.shields.io/badge/MetaCubeXD-v1.271.0-purple.svg)](https://github.com/metacubex/metacubexd)

> Mihomo Dashboard — 代理面板，管理规则、节点、连接。支持直连内网 Mihomo API。
>
> Mihomo Dashboard — manage rules, nodes, and connections. Connects directly to local Mihomo API.

将 [MetaCubeXD](https://github.com/metacubex/metacubexd) 打包为飞牛 NAS (fnOS) 桌面窗口应用。

---

## 快速开始 / Quick Start

1. 从 [Releases](https://github.com/techysy/metacubexd-fnos/releases) 下载 `metacubexd-x.x.x.fpk`
2. 飞牛 App Center → **手动安装** → 选择 fpk 文件
3. 桌面出现 **MetaCubeXD** 图标，点击打开面板（端口 9091）
4. 面板自动连接 Mihomo API（默认 `http://192.168.31.31:9090`）

## 应用设置 / App Settings

安装后可在 **App Center → 应用设置** 中配置 Mihomo API 地址，无需手动改代码：

| 设置项 | 默认值 | 说明 |
|---|---|---|
| Mihomo API 地址 | `http://192.168.31.31:9090` | Mihomo 的 external-controller 地址 |

修改后需**重启应用**生效（App Center → 停止 → 启动）。

## 端口 / Port

- **面板端口**：9091
- **Mihomo API**：9090
- **Mihomo HTTP 代理**：7890

## ⚠️ 远程访问注意事项（混合内容）

通过 **fnOS 远程访问（`https://<app>.techysy.fnos.net` / FN Connect）** 打开面板时，面板页面以 **HTTPS** 加载，而 Mihomo 后端是 **HTTP**（`http://192.168.31.31:9090`），浏览器会因**混合内容**拦截请求，面板报"连接被阻止 / Connection blocked"。

**关键点**：
- 换成 `type: "url"`（新标签页）**无法解决** —— 新标签页仍是 HTTPS 加载，混合内容拦截是浏览器级策略，与 iframe/url 无关
- 且 Mihomo 是**局域网地址**，外网设备也连不到

**可行方案**：
1. **局域网直连**：直接浏览器访问 `http://192.168.31.101:9091`（HTTP），面板 HTTP 加载连 HTTP 后端，无混合内容
2. **fnOS 桌面 Chrome**（fygo-browser 应用）：直接在飞牛本机打开 `http://127.0.0.1:9091` 或 `http://192.168.31.31:9090/ui`，浏览器跑在 NAS 上，HTTP 加载 + 内网可达，完全绕过问题
3. **暴露公网 HTTPS**：把 Mihomo 反向代理成公网 HTTPS 地址（成本较高）

> 详尽的排查记录见 [`fnos-integration-pitfalls.md`](https://github.com/techysy/fnos-app-dev-skill/blob/main/references/fnos-integration-pitfalls.md)（私有仓库）

## 🔮 Future / 迭代计划

等待上游 [metacubex/metacubexd](https://github.com/metacubex/metacubexd) 发布新版本后重新打包：

- 跟进上游版本更新（新功能、Bug 修复）
- 新增节点类型/协议支持
- 面板 UI/UX 优化

> 📖 上游项目：[metacubex/metacubexd](https://github.com/metacubex/metacubexd) · [在线 Demo](https://metacubex.github.io/metacubexd/)

## 相关链接 / Links

- [Hermes WebUI](https://github.com/techysy/hermes-webui-fnos) — Hermes 相关 fnOS 应用（WebUI 浏览器访问）
- [9Router](https://github.com/techysy/9router-fnos) — Hermes 相关 fnOS 应用（FREE AI 路由器 / API 代理）
- [Strava Panel](https://github.com/techysy/strava-panel-fnos) — Hermes 相关 fnOS 应用（Strava 骑行数据面板）
- [fnOS 开发者文档](https://developer.fnnas.com/docs/guide)

## License

MIT — 与 [metacubex/metacubexd](https://github.com/metacubex/metacubexd) 一致
