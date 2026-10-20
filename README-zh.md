# Pixel 套件（简体中文版）

> 本仓库是 [RovianDev/PixelSuite](https://github.com/RovianDev/PixelSuite) 的简体中文分支。
> 功能、行为与原版完全一致，只把界面文案、模块描述和应用名称换成了中文。

你的 Pixel，按你的方式来。

原作者 **RovianDev**。这是一个免费开源的 LSPosed 模块，用于 Pixel 手机的自定义、应用与文件夹锁定、手势、截图工具和文件排序。每个功能都有独立开关。

**从主屏幕打开 Pixel 套件：** 长按空白处，然后选择 **Pixel 套件设置**。

## 中文化做了什么

| 项目 | 说明 |
| --- | --- |
| 应用名 | `Pixel 套件`（`res/values-zh-rCN/strings.xml`） |
| 模块描述 | LSPosed 里显示的简介已改为中文（`src/meta/xposed/module.prop`） |
| 界面文案 | 约 190 条硬编码在 Java 里的英文文案，通过 `Zh.java` 运行时词典译为中文 |
| 保留英文键 | 部分代码用英文原文做行匹配（如 `PromptStyle` 的 `Pin`、`PrivacyFolders` 的 `Remove`），因此词典以英文为键、只在显示时替换 |

`Zh.java` 是唯一的翻译表。想改某句话，直接改这张表里的中文即可，不必动逻辑代码。

## 构建（不需要本地环境）

推送到 `main` / `zh` 分支，或在 Actions 页面手动运行 **构建中文版 APK** 工作流。

产物：`PixelSuite-zh-unsigned.apk`（**未签名**，只做了 4 字节对齐）。

下载后需要自行签名才能安装：

```bash
# 用你自己的 keystore 签名
apksigner sign --ks my-release.keystore --out PixelSuite-zh.apk PixelSuite-zh-unsigned.apk
```

也可以用 `uber-apk-signer` 或 MT 管理器直接签。

## 原版说明

完整功能列表、更新日志和发布说明见 [原仓库](https://github.com/RovianDev/PixelSuite) 与 [README.md](README.md)。
