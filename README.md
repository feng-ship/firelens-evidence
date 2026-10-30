# FireLens 火情循证助手

基于 [LeonardoSya/firelens-nextjs](https://github.com/LeonardoSya/firelens-nextjs) 的MIT许可源码改进，原作者版权保留。将区域火点查询、观测统计、原始记录、AI解读和证据导出关联到同一次查询。

![真实工作台运行结果](workbench-preview.png)

## 下载与运行

由于采用GitHub网页上传，本仓库以完整源码包提供文件，目录层级保存在压缩包内。**先下载并解压 [firelens-evidence-source.zip](firelens-evidence-source.zip)**，进入其中的 `firelens-evidence` 文件夹，再执行以下命令。不要在只有ZIP的仓库根目录直接运行npm。源码包内含123个文件，包括应用源码、测试、文档、固定数据压缩文件与许可。

使用Node.js 26（本机验证26.3.0）与pnpm 9：

```bash
pnpm install --frozen-lockfile --ignore-scripts
node scripts/restore-snapshot.mjs
npm run dev
```

打开 http://localhost:3000/zh/evidence，保持启动终端开启。基础查询不需要地图Token、数据库或模型账号；AI解释需使用者自己的可用授权。详细说明见解压后的README.md与docs/AI接入-ChatGPT套餐.md。

## 演示案例

选择云南附近、最低FRP为0、置信度全部；时间为2026-10-25 00:37至2026-10-27 13:19 UTC。固定快照得到273条观测，最大FRP为41.75 MW，记录N21-113956。数据为NASA FIRMS / NOAA-21 VIIRS C2历史快照，共143,998条，校验脚本验证SHA-256后恢复CSV。

观测数不是独立火灾次数，矩形范围不是行政区边界。当前缺少气象与NDVI，不生成对应风险判断，不推断过火面积、蔓延或碳排放。

## 改进与验证

- 统一时空条件、筛选、统计、显示和记录标识。
- 缺失气象不填默认值；空结果与时段未覆盖分别提示。
- 服务端重算证据后请求AI解释，显示模型、完成时间、查询标识；可导出JSON核查。
- 提供独立参考计算、校验节点和测试。

匿名原始记录可下载 [verification-records.zip](verification-records.zip)。已有28项TypeScript测试、8项Python测试、类型检查、干净副本生产构建和5组接口检查通过。构建验证复用了既有安装依赖，未声称全新联网安装或全仓lint通过。3个真实模型联调样例与10个定向节点对照分别记录，不代表总体准确率。截图为2026-10-29成功结果，与10月28日的历史下载核对分开记录。

完整测试另需Python 3与Ruby。解压后可运行npm test、python3 tests/workflow_test.py。源码包内含CI工作流模板，但压缩包中的工作流不会自动在此仓库运行；未声称远端CI通过。

## 来源与许可

上游提交796a890d432318c156a6851e7456007e881bac5e；MIT许可与Copyright (c) 2024 Zhang YiYang保留。原地图和既有架构属于上游基础，新增范围见包内docs/CHANGELOG-AIC.md。第三方数据、字体和在线服务按各自条款使用，详见 [NOTICE](NOTICE.md)、[LICENSE](LICENSE) 与 [UPSTREAM.json](UPSTREAM.json)。

代码、测试和材料使用生成式AI辅助；已有验证范围如实披露，不将上游、卫星产品或基座模型认作从零原创。无用户试用、软著、论文发表或上游PR合并证明。源码包不含账号Token、.env.local、node_modules、原带凭据工作流或原后端。参赛报告和视频另交比赛系统，不在此仓库公开。
