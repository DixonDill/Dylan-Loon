# Dylan-Loon

Dylan 的 Loon 分流规则与插件仓库。所有规则内容都镜像/合并存放在本仓库，Loon 只订阅本仓库的链接，统一走 jsDelivr CDN 分发。

## 仓库结构

- `rules/` — 全部远程规则文件（本地规则按软件拆分 + 第三方订阅镜像/合并）
- `plugins/` — Loon 插件
- `loon.conf` — 配置片段：把 `[Remote Rule]` 整段并入自己的配置即可，另有两条必须留在本地的规则

## 订阅链接（jsDelivr，策略见 loon.conf）

本地规则按软件拆分：

- Music（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Music.list
- JavDB（HK AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/JavDB.list
- JavDB-JP（JP AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/JavDB-JP.list
- Bybit（JP AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Bybit.list
- LAN（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/LAN.list
- Misc（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Misc.list
- Misc-HK（HK AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Misc-HK.list

合并/镜像的远程规则：

- AIGC（JP AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/AIGC.list
- Apple（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Apple.list
- PanVod（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/PanVod.list
- WeChat（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/WeChat.list
- TestFlight（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/TestFlight.list
- Douyin（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Douyin.list
- Talkatone（Final）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Talkatone.list
- Telegram（HK AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Telegram.list
- TikTok（US AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/TikTok.list
- Netflix（SG AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Netflix.list
- YouTube（HK AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/YouTube.list
- Google（HK AUTO）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Google.list
- ChinaASN（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/ChinaASN.list
- GeoIP-CN（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/GeoIP-CN.list
- LAN-Splitter（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/LAN-Splitter.list
- Region-Splitter（DIRECT）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/rules/Region-Splitter.list

插件：

- 示例插件（模板）：https://cdn.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/plugins/example.plugin

## 说明

- 规则文件内包含多个软件/服务时，用 `# 名称` 分节、分节之间空行，便于区分。
- 合并说明：AIGC.list = 上游 AIGC 357 条 + Muse 未被覆盖的 4 条（共 361 条），原 Muse 订阅不再单独保留；PanVod.list = 上游 PanVod 47 条 + 本地 115 的 IP 规则 1 条（共 48 条），本地 115 其余 4 条已被 PanVod 的 `DOMAIN-SUFFIX,115.com` 覆盖，不再单列。
- 镜像为 2026-11-25 快照，各文件头注释里有上游来源；上游更新不会自动同步，需要时重新抓取覆盖。
- jsDelivr 对 `@main` 链接有缓存：改完文件后急用可访问 `https://purge.jsdelivr.net/gh/DixonDill/Dylan-Loon@main/文件路径` 强制刷新，再在 Loon 里手动更新。规则都是下载到本地后运行，更新延迟不影响日常上网速度。
