# 回声 Recall · 可执行文件下载

> 回声 Recall - 主动型桌面上下文记忆助理
> 把你在电脑前流逝的工作上下文，变成可行动的记忆和提醒。

---

## 下载 Recall 0.1.0

### 方式一：NSIS 安装包（推荐）

[**Recall-0.1.0-setup.exe**](./dist/Recall-0.1.0-setup.exe) — 91 MB
适合 Windows 10/11 用户。NSIS 安装包，可选安装路径、桌面/开始菜单快捷方式。

### 方式二：免安装绿色版

[Recall.exe (绿色版)](https://github.com/xscanzm/recall-releases/releases/download/v0.1.0/Recall.exe) — 178 MB
解压到任意目录双击运行，**未做代码签名**，首次启动 Windows Defender 可能提示。

> 安装后桌面会出现 **Recall** 图标，首次启动会引导你配置模型 API Key。

### 校验

下载后请校验 SHA256，确保文件完整未篡改，校验值见 [SHA256SUMS.txt](./SHA256SUMS.txt)。

Windows PowerShell:

```powershell
Get-FileHash .\Recall-0.1.0-setup.exe -Algorithm SHA256
```

---

## 这是什么

回声 Recall 获得你的授权后，会观察你在电脑前的工作活动，把原本会自然流失的上下文转化为结构化记忆、任务追踪、项目进展、应用内提醒、日报和周报。

- 截图只作模型输入，**默认保留当天**，UI 不展示截图墙
- **L0 → L1 → L2 → L3 记忆自动生长**，你通过编辑、删除、合并来修剪
- 主动生成应用内提醒，**桌面通知默认关闭**
- **自带 API Key**，模型调用直连你配置的 endpoint
- **本地优先**：截图与数据库全在本地，不上传到 Recall 自有服务器

---

## 快速开始

1. 下载 `Recall-0.1.0-setup.exe` 并双击安装。
2. 启动 Recall，进入「模型配置」：填入你自带的 OpenAI-compatible 端点的 `endpoint / model / API Key`。
3. 前往「设置 → 隐私」确认默认黑名单应用和截图保留策略。
4. 点击「**开始观察**」。

---

## 隐私与信任

Recall 不收集任何遥测数据，不上传截图，不内置任何远程服务。

- 截图仅保存在用户本地 `appData` 缓存目录，文件名不含窗口标题或 URL
- API Key 通过系统级安全存储（Windows Credential Manager），不进 SQLite
- 模型调用直连用户自配的 endpoint，不经过 Recall 自有服务器
- 完整源码公开在 **[xscanzm/recall](https://github.com/xscanzm/recall)**，可自行审计、fork、构建

如发现安全问题，请在 [xscanzm/recall/issues](https://github.com/xscanzm/recall/issues) 提交。

---

## 想看代码或自己构建？

- 主仓库（源码 + 完整产品说明）：**[github.com/xscanzm/recall](https://github.com/xscanzm/recall)**
- 构建指南：见主仓库 `README.md` 的「开发者构建」一节
- 27 份产品规格与施工规格：见主仓库 `doc/`

---

## 版本历史

见 [CHANGELOG.md](./CHANGELOG.md)。

---

## 许可证

本项目以 **Business Source License 1.1 (BUSL-1.1)** 发布。
完整文本见 [LICENSE](./LICENSE)。

- ✅ 源码完全可见，可审计与学习
- ✅ 个人非生产使用、修改、内部研究允许
- ❌ 禁止生产环境商用（SaaS、再分发、商业产品集成），需另行授权
- ⏰ 变更日期 **2030-07-08**：届时自动转为 **Apache License 2.0**
