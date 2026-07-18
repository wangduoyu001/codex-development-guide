# 仓库地图与职责边界

GitHub 账号：`wangduoyu001`

## 核心仓库

### AI Director

- 地址：https://github.com/wangduoyu001/ai-short-drama-production-controller
- 职责：剧本、分镜、资产规划、提示词、制作合同、导演控制和质量门禁
- 不负责：GPU 生命周期、ComfyUI Worker、云执行平台

### Comfy Cloud Platform

- 地址：https://github.com/wangduoyu001/comfy-cloud-platform
- 职责：Workflow、Provider、Worker、任务队列、生成 API、云 GPU 与模型执行适配
- 不负责：剧情理解、导演创作规则和资产决策

### LingJi

- 地址：https://github.com/wangduoyu001/lingji
- 职责：第二大脑、知识采集、RAG、向量索引、机会发现、控制中心和 Obsidian 协同
- 不负责：短剧生成执行层和 ComfyUI Worker

### Obsidian

- 地址：https://github.com/wangduoyu001/obsidian
- 可见性：私有
- 职责：知识库和人工编辑入口
- 规则：未经明确要求，不批量改写、删除或重构用户知识内容

## 参考与辅助仓库

### Toonflow App

- 地址：https://github.com/wangduoyu001/Toonflow-app
- 用途：节点画布、UI 和工作台交互参考
- 规则：不是正式 AI 导演主仓库

### PEMIS LingJi

- 地址：https://github.com/wangduoyu001/pemis-lingji
- 用途：灵机旧版历史与迁移参考
- 规则：新功能默认进入 `lingji`

### Social Auto Upload

- 地址：https://github.com/wangduoyu001/social-auto-upload
- 用途：多平台发布工具

### Douyin Upload Tool

- 地址：https://github.com/wangduoyu001/Douyin-Automated-Multi-Account-Batch-Upload-Tool
- 用途：抖音多账号批量上传

### MediaCrawler

- 地址：https://github.com/wangduoyu001/MediaCrawler
- 状态：开发前先确认是否仍在使用

### Hongguo Drama Downloader

- 地址：https://github.com/wangduoyu001/hongguo-drama-downloader
- 用途：下载工具

### Strix

- 地址：https://github.com/wangduoyu001/strix
- 用途：安全研究与参考，仅限合法授权范围

### Obsidian Translations

- 地址：https://github.com/wangduoyu001/obsidian-translations
- 用途：Obsidian 翻译辅助

## 系统边界

推荐链路：

`LingJi / 用户输入 → AI Director → 结构化生产任务 → Comfy Cloud Platform → 模型或 GPU → 资产 → QA 与版本记录`

禁止把导演规则复制进 Comfy 执行层，也禁止把云 GPU 调度塞进 AI Director。
