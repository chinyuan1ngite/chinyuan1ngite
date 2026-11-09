# 产品作品集

我的三个项目分别面向短剧分镜、政务产品协作和电商商品草稿。每个项目都附有可试用的入口和验证范围。

## 01 · 短剧分镜生成 Skill

[storyboard-skill-v0.4-tester](https://github.com/chinyuan1ngite/storyboard-skill-v0.4-tester)

- **解决的问题**　把短剧本拆成可检查的镜头，减少逐镜重写提示词时遗漏对白、动作和镜头连续性的问题。
- **系统架构**　剧本 → Agent 按场景加载镜头规则 → 结构化分镜（Storyboard IR）→ 校验 → 确定性适配器生成 Seedance 2.0 提示词。
- **演示方式**　按[快速上手](https://github.com/chinyuan1ngite/storyboard-skill-v0.4-tester/blob/main/QUICKSTART.md)输入一段 5–20 秒短剧本，对照分镜与逐镜提示词，也可独立运行工具链冒烟测试。
- **测试成果**　14 个路由／分镜／提示词回归用例，42/42 条提示词逐字节一致。[验证记录](https://github.com/chinyuan1ngite/storyboard-skill-v0.4-tester/blob/main/LIMITATIONS.md#已经验证)
- **已知限制**　真实视频效果、口型和声音连续性仍待验证。试生成视频需自行使用 Seedance 服务。

## 02 · 政务产品工作流与视觉设计 Skills

[1gnite-pm-skills](https://github.com/chinyuan1ngite/1gnite-pm-skills)

- **解决的问题**　让产品经理和 Agent 从同一套需求事实出发，减少 PRD、原型、权限台账和验收用例之间的口径偏差。
- **系统架构**　项目口径库和 `AGENTS.md` 约束协作，稳定编号贯穿 PRD → HTML 原型 → 结构化台账 → 测试验收。视觉层由通用生图 Skill 和带政务规范、任务路由与参考图的项目适配 Skill 组成。
- **演示方式**　从[单位管理案例](https://github.com/chinyuan1ngite/1gnite-pm-skills/tree/main/examples/government-project-product-workflow)对照 PRD 和台账，下载仓库后用浏览器打开 HTML 原型，试走查询、新增和编辑流程。
- **测试成果**　[验收表](https://github.com/chinyuan1ngite/1gnite-pm-skills/blob/main/examples/government-project-product-workflow/07_%E6%B5%8B%E8%AF%95%E9%AA%8C%E6%94%B6/%E5%8A%9F%E8%83%BD%E6%B5%8B%E8%AF%95%E7%82%B9.csv)列出 8 个测试点，包含接口异常和无权限状态，执行状态均为「未执行」。
- **已知限制**　公开版仅保留一条脱敏业务链路，原型使用示例数据，视觉 Skill 输出概念稿。

## 03 · 1688 商品草稿工具

[commercial-draft-tool](https://github.com/chinyuan1ngite/commercial-draft-tool)

- **解决的问题**　减少手工采集商品、核对 SKU 和图片、重复填写卖家后台的工作量，正式发布由人工审核。
- **系统架构**　Windows 桌面端／CLI → 1688 采集器 → 本地商品与素材校验 → 隔离的卖家 Chrome 会话填充 → 草稿保存与重开核验。[架构文档](https://github.com/chinyuan1ngite/commercial-draft-tool/blob/main/docs/architecture.md)
- **演示方式**　用[离线合成样例](https://github.com/chinyuan1ngite/commercial-draft-tool/blob/main/examples/README.md)运行 `--validate-only`，对比正常商品和缺少标题的商品各自的校验结果，无需登录。
- **测试成果**　0.4.24 的回归记录有 175 项通过，其中 56 项使用隔离 Chrome。[测试记录](https://github.com/chinyuan1ngite/commercial-draft-tool/blob/main/docs/compatibility.md#自动回归与现场验收)
- **已知限制**　当前面向 Windows 和 Chrome 上的 1688 流程，真实店铺端到端验收待补，视频和其他平台尚未支持。
