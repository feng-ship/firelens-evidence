# 来源与许可说明

本项目基于 LeonardoSya/firelens-nextjs 的 MIT 许可源码进行增量开发。上游固定提交为 796a890d432318c156a6851e7456007e881bac5e，版权声明 Copyright (c) 2024 Zhang YiYang 保留于 LICENSE。上游地址与恢复过程见 UPSTREAM.json。当前仓库不冒充上游仓库，也不声称从零开发了其地图、交互及既有架构。

本轮新增代码按仓库 MIT 许可提供；第三方依赖、字体、数据与在线服务仍适用各自条款，不能将整个技术栈表述为 MIT。

- NASA LANCE FIRMS / NOAA-21 VIIRS C2 数据：保留来源、采集时间、快照校验值及官方引用与免责声明链接，详见 docs/aic/数据引用说明.md。数据不因本仓库 LICENSE 而变为 MIT；不暗示 NASA/NOAA 背书。
- Tiny5 字体：The Tiny5 Project Authors，SIL Open Font License 1.1。许可全文见 public/fonts/OFL-Tiny5.txt，字体不改用 MIT。
- Mapbox GL、地图服务、ChatGPT 账号授权与模型服务适用各自许可或服务条款；不分发用户账号、Token 或付费服务访问权。
- 原 firelens-deno 后端与原带凭据 Dify 导出不在此源码包内；本地原节点对照结果只以不含凭据的记录提供，不构成原导出的再分发授权。

代码、测试、流程及文档使用生成式 AI 辅助编写。已有验证包括程序测试、独立参考计算、接口核对和少量真实模型联调；团队应据实际操作确认并记录审核、修改和验证工作，不将 AI 生成内容直接等同于个人从零研发成果。
