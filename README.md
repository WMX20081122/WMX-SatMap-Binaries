# WMX SatMap · 二进制发行

给 Minecraft 基岩版专用服务器做主世界、下界和末地的网页地图，支持平面俯视和三维浏览。

本仓库仅托管二进制发行说明及下载，不含 SatMap 源码、BDS、加载器、世界存档、测试地图或私人试验包。

## 下载：先选加载器，再选系统

SatMap 提供 **Endstone 和 LeviLamina 两种适配版**。一个包只能给对应加载器使用；不用同时安装两个加载器，也不要把三个包都解压到同一台服务器。

| Release 附件 | 系统 | 实测加载器 / BDS | 解压位置 |
|---|---|---|---|
| `WMX-SatMap-Endstone-1.0.0-beta.3-windows-x64-binary.zip` | Windows x64 | Endstone `0.11.15` / BDS `1.26.60.6` | 合并服务器根目录下的 `plugins/` |
| `WMX-SatMap-Endstone-1.0.0-beta.3-linux-x64-binary.zip` | Linux x64（glibc） | Endstone `0.11.15` / BDS `1.26.60.6` | 合并服务器根目录下的 `plugins/` |
| `WMX-SatMap-LeviLamina-1.0.0-levi-trial.1-windows-x64-binary.zip` | Windows x64 | LeviLamina `v26.60.9` / BDS `1.26.60.6` | 合并服务器根目录下的 `mods/` |

在本仓库的 **Releases** 下载对应 ZIP。Windows 需要 Microsoft Visual C++ v14 x64 运行库。LeviLamina 版未提供 Linux 或 ARM64 包，不要与 BDS `1.26.66.1` 混用。

## 出图前需要配套渲染资源

**公开的三个附件都不含渲染素材，单独下载后不能直接出图。** 请从你有权使用的来源取得与配置哈希匹配的 `mapping_ext.bin`、`models_integrated_canonical.bin`、`textures.json.gz`，不要关闭校验。

- **Endstone**：渲染资源放入 `plugins/wmx_satmap/assets/`，配置放入 `plugins/wmx_satmap/config.json`。
- **LeviLamina**：渲染资源放入 `mods/wmx-satmap/data/assets/`，配置放入 `mods/wmx-satmap/data/config.json`。
- 将相应包内的 `config.example.json` 另存为 `config.json`，把 `paths.worldPath` 改为 BDS 当前世界的绝对路径，末尾不加 `/db`。
- 用对应加载器开服，在控制台手动执行 `satmap render all`，用 `satmap status` 看进度。网页默认仅监听服务器本机 `127.0.0.1:5110`。发布后先选维度，再切换平面俯视。

这些是隔离环境实测的试验构建，不能据此推断其他版本、玩家连接或生产大图表现。保留旧地图代时也要预留磁盘。

GitHub Release 可能额外显示自动生成的 `Source code` ZIP/TAR；它们只是仓库标签快照。如果仓库只保留这份 README，快照也只包含 README，不会有 SatMap 项目源码。

致谢 [Endstone](https://github.com/EndstoneMC/endstone)、[LeviLamina](https://github.com/LiteLDev/LeviLamina) 和 [BlueMap](https://github.com/BlueMap-Minecraft/BlueMap)。
