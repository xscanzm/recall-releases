# Changelog

## 0.1.0 (2026-07-08)

首个 Alpha 公开发布。

### 新增
- 多模态统一模型架构：单次模型调用完成观察+抽取+关联+判断
- L0 → L1 → L2 → L3 记忆自动生长与编辑/删除/合并/纠错
- 今日页时间轴 + 右侧上下文面板
- 双轨报告：工作日报 + 个人复盘
- 应用内主动提醒，桌面通知默认关闭
- 完整的本地搜索（facts / scenes / projects / reports / tasks）
- 设置与信任中心（模型配置、截图保留、黑名单、通知、数据管理）
- 27 份产品规格与施工规格文档（见主仓库 `doc/`）

### 体验升级（来自多模态架构改造）
- 模型类型从 2 种变 1 种（只需配置多模态）
- 单次 capture 的模型调用从 4-5 次降为 2 次
- 模型队列从 2 个合并为 1 个
- 并发上限统一为 3
- pipeline 步骤从 5 步降为 3 步

### 兼容性
- Windows 10 / 11 (x64)
- 需要自备 OpenAI-compatible 多模态端点的 API Key

### 已知限制
- 仅 Windows x64
- 无多端同步
- 无云备份
- 无代码签名（首次启动 Windows Defender 可能提示）
- 绿色版 (Recall.exe, 178MB) 超过 GitHub 单文件 100MB 限制，请从 [GitHub Releases](https://github.com/xscanzm/recall-releases/releases) 下载

### 详细信息
- 完整审计报告：主仓库 `doc/m3审核.md`
- 完整规格文档：主仓库 `doc/`
- 主仓库：https://github.com/xscanzm/recall
