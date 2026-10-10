![GlassPad](assets/social-preview.png)

# GlassPad

macOS 原生 Launchpad 替代工具，采用 Liquid Glass 美学，全面支持无限屏画布、实时桌面壁纸捕获。

**本仓库为公开发布页**：只放版本标记、更新日志与安装包，**不含任何源码**。

## 下载 / Download

- **官方站点（下载 / 更新日志）：[glasspad.pocketbay.app](https://glasspad.pocketbay.app/)**
- **Releases（本仓库）：[GlassPad-1.0.307.dmg](https://github.com/anson55sky/GlassPad/releases/tag/v1.0.307)**
- 所有历史版本见 [Releases](https://github.com/anson55sky/GlassPad/releases)

## ⚠️ 开始前请先做一步（macOS 27 必读）

macOS 27 的四指捏合由**系统手势引擎直接接管，程序无法从内部关闭它**。要让它只唤起 GlassPad，需要你在系统设置里让出这两个手势：

**系统设置 → 触控板 → 更多手势**，把下面两项关掉：

| 开关 | 手势 | 说明 |
|---|---|---|
| **App** | 捏拢拇指和其他三指 | 系统的 App 面板 |
| **显示桌面** | 张开拇指和其他三指 | 系统的「显示桌面 / 推窗口」 |

关掉后：四指捏合只唤起 GlassPad；玻璃板关闭时，四指张开保持系统原生的「显示桌面」行为。

> GlassPad **从不写入你的任何系统偏好**。状态栏图标右键菜单里有「**关闭系统四指手势（打开系统设置）**」，点一下可直接跳到该页面。

**截图示意：**

| 关闭后（推荐） | 打开时（会冲突） |
|---|---|
| ![关闭后](https://raw.githubusercontent.com/anson55sky/GlassPad/main/assets/setup/gestures-off.png) | ![打开时](https://raw.githubusercontent.com/anson55sky/GlassPad/main/assets/setup/gestures-on.png) |

## 安装 / Install

1. 下载 `.dmg`，将 **GlassPad** 拖入「应用程序」。
2. 首次打开若被 Gatekeeper 拦截：右键 App →「打开」，或在 **系统设置 → 隐私与安全性** 中点击「仍要打开」。
   （当前为 ad-hoc 签名、尚未公证 Notarize，属正常提示。）
3. 首次启动后请授予**辅助功能**权限 —— 四指手势接管依赖它。
4. **壁纸权限说明**：静态图片壁纸无需任何权限；动态/Aerials 壁纸的高保真实时捕获可能需要「完全磁盘访问」，未授权时自动降级为系统资源，不会空白。

## 更新日志 / Changelog

### v1.0.307 · 移除残留自愈

- 移除 1.0.306 后残留的 `cleanupLegacyWrites` 自愈 —— 它把用户在系统设置里手动关闭的四指手势判作旧版本残留并删掉，悄悄恢复系统手势。
- GlassPad 此后永远「不写入、不删除」你的系统偏好，只读探测 + 状态栏直达系统设置。

### v1.0.306 · 手势冲突根治

- 四指捏合与四指张开全面对齐 Buho：捏合只唤起 GlassPad，系统 App 面板不再常驻弹出；玻璃板关闭时四指张开保持系统原生行为。
- **移除全部修改系统偏好的代码** —— GlassPad 从不写入你的系统设置，只在状态栏提供「打开系统设置」快捷入口。
- 修复 App 内自动更新此前指向私有仓库导致恒 404 的问题。
- 修复站点下载端点版本号写死导致「更新后仍下载到旧包」的问题。

### v1.0.248 – 1.0.250 · 隐私 + 手势接管

- **壁纸改用系统壁纸窗口接口抓取，彻底去掉录屏（屏幕录制）授权**。
- 四指捏合改由 CGEventTap 接管，退出时完整归还给系统。

### v1.0.251 – 1.0.262 · 文件夹延伸

- 文件夹面板改为横向撑开，刚体缩放取代逐图标飞行；锚点锁定到被点 badge 中心。

### v1.0.262 – 1.0.269 · 开合对齐

- 主页面开合节奏对齐 Buho；不再收走系统菜单栏，顺带根治打开时 Dock 闪烁。

### v1.0.153 – 1.0.190 · 手势与动效

- 捏合召唤全程跟手；修复慢速捏合卡死、手势期四角变尖角；玻璃色调持久化修复；文件夹支持滚轮翻页。

## 自动更新 / Auto-update

App 内「设置 → 检查更新」会比对本仓库与官网的 Releases。

## 许可与发布策略 / License & Distribution

- 当前为 **内测版（Open Beta）**，**全部功能免费，无需激活码**。
- **源码不公开**，本仓库仅存放版本存档、更新日志与安装包。
- 站内下载统一走官网 [glasspad.pocketbay.app](https://glasspad.pocketbay.app/)。