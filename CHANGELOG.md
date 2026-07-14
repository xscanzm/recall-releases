# Changelog

## 0.1.0 (2026-07-08)

### 2026-07-14 记忆搜索 FTS、人物关系与 UI 细节优化
- 新增 observation_search_fts 与 person_relationship 数据库迁移
- 扩展 MemorySearchRepository/IPC handlers 并补充单测
- 优化 AppShell/StatusPill/Timeline 组件与 logo 主题样式
- 完善 PeoplePage 人物页交互与 schemas/prompts 契约
- 更新 .gitignore 排除本地构建产物与发布仓库

### 2026-07-13 模型配置简化与 URL 兼容性优化
- 模型配置表单简化：默认只显示 Endpoint URL、Model 名称、API Key 三个必填字段
- Provider 名称、温度、最大输出长度折叠到「高级设置」，降低新用户配置门槛
- Provider 名称改为可选，留空时自动用 Model 名称填充
- 修复 normalizeEndpoint 未处理 /v1 的 bug：后台统一去除末尾 /v1 并补全为 /v1/chat/completions
- URL 兼容性提升：无论用户是否带 /v1 后缀，后台都能正确调用

首个 Alpha 公开发布。

### 2026-07-11 记忆系统可靠性更新
- 严格活动窗口截图匹配，补齐高敏感与立即删除截图的生命周期清理
- 新增 SQLite 持久批次、失败重试、异常退出恢复和 Observation 幂等写入
- 今日时间轴改为 10 分钟成熟窗口 + 30 分钟可变尾部，连续事项按约 8-15 分钟自然聚合
- 时间轴尾卡替换与 checkpoint 事务化，保护日报、报告和待收尾引用的卡片
- 忘记/清空事务化，按本地自然日删除；迁移失败保留原库并阻止静默空库
- 新增 FTS5 统一搜索和不截断的完整结构化数据导出
- 增加 Windows 登录自启动、首次观察选择、异常退出诊断和可靠退出
- 建立 Vitest、真实 SQLite 集成测试、Electron E2E 与 Windows CI

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
