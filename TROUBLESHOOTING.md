# TROUBLESHOOTING / 故障排除

---

## 远程访问时面板报"连接被阻止 / Connection blocked"（混合内容）

**症状**: 通过 fnOS 远程访问（`https://<app>.techysy.fnos.net` / FN Connect）打开面板，报"连接被阻止 / Connection blocked"。

**原因**: 面板页面以 **HTTPS** 加载，而 Mihomo 后端是 **HTTP**（`http://192.168.31.31:9090`），浏览器因**混合内容（mixed content）**策略拦截了 HTTP 请求。

**关键点**:

- 换成 `type: "url"`（新标签页）**无法解决** —— 新标签页仍是 HTTPS 加载，混合内容拦截是浏览器级策略，与 iframe/url 无关
- 且 Mihomo 是**局域网地址**，外网设备也连不到

**可行方案**:

1. **局域网直连**：浏览器访问 `http://192.168.31.101:9091`（HTTP），页面 HTTP 加载连 HTTP 后端，无混合内容
2. **fnOS 桌面 Chrome**（fygo-browser 应用）：飞牛本机打开 `http://127.0.0.1:9091` 或 `http://192.168.31.31:9090/ui`，浏览器跑在 NAS 上，HTTP 加载 + 内网可达，完全绕过
3. **暴露公网 HTTPS**：把 Mihomo 反向代理成公网 HTTPS 地址（成本较高）

> 详尽的排查记录见 [`fnos-integration-pitfalls.md`](https://github.com/techysy/fnos-app-dev-skill/blob/main/references/fnos-integration-pitfalls.md)（私有仓库）
