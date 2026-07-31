# MetaCubeXD fnOS App

[![GitHub release](https://img.shields.io/github/v/release/techysy/metacubexd-fnos?label=Latest&color=blue)](https://github.com/techysy/metacubexd-fnos/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/techysy/metacubexd-fnos/blob/main/LICENSE)
[![fnOS 1.1.31xx](https://img.shields.io/badge/fnOS-1.1.31xx+-orange.svg)](https://developer.fnnas.com/docs/guide)
[![MetaCubeXD v1.270.6](https://img.shields.io/badge/MetaCubeXD-v1.270.6-purple.svg)](https://github.com/metacubex/metacubexd)

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

## 🔮 Future / 迭代计划

等待上游 [metacubex/metacubexd](https://github.com/metacubex/metacubexd) 发布新版本后重新打包：

- 跟进上游版本更新（新功能、Bug 修复）
- 新增节点类型/协议支持
- 面板 UI/UX 优化

> 📖 上游项目：[metacubex/metacubexd](https://github.com/metacubex/metacubexd) · [在线 Demo](https://metacubex.github.io/metacubexd/)

## License

MIT — 与 [metacubex/metacubexd](https://github.com/metacubex/metacubexd) 一致
