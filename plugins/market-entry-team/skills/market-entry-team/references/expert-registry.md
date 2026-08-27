# 专家注册表

本文件把业务角色绑定到 Skill 内部的独立专家合同。专家行为、判断边界和专属输出要求随 Skill 一起分发；共享证据、项目结构和编排规则继续由其他公共文件维护。

| 业务角色 | 专家合同文件 | 当前扩展 |
|---|---|---|
| 法规专家 | `references/experts/regulatory-expert.md` | 无专属模型、Skill或MCP |
| 市场渠道与竞品专家 | `references/experts/market-channel-expert.md` | 无专属模型、Skill或MCP |
| 消费者专家 | `references/experts/consumer-expert.md` | 无专属模型、Skill或MCP |
| 产品与品牌专家 | `references/experts/product-brand-expert.md` | 无图像模型、专属Skill或MCP |
| 品牌增长与用户转化专家 | `references/experts/brand-growth-expert.md` | 无专属模型、Skill或MCP |
| 渠道进入与铺货专家 | `references/experts/channel-growth-expert.md` | 无专属模型、Skill或MCP |
| 商业模式与行动计划专家 | `references/experts/business-planning-expert.md` | 无专属模型、Skill或MCP |
| 组织与人才配置专家 | `references/experts/organization-talent-expert.md` | 仅用户或指定决策负责人明确表达招聘、岗位设计或团队配置意图时触发；无专属模型、Skill或MCP |
| 独立审查专家 | `references/experts/independent-reviewer.md` | 无专属模型、Skill或MCP |

## 调用规则

1. 项目总控根据`orchestration.md`选择业务角色后，只读取本表对应的专家合同，并把完整合同交给为该角色创建的子 Agent。
2. 创建任务时还必须传入目标市场、产品、问题、共享规则路径、可读文件和唯一目标文件；专家合同不能代替具体任务说明。
3. 未经用户要求，不在运行时临时更换专家模型、添加MCP、启用图像生成或扩大工具权限。
4. 本 Skill 不依赖用户个人目录中的自定义 Agent 配置。只要运行环境支持子 Agent，就按专家合同创建对应角色。
5. 后续修改某位专家的职责、输出或专属工具时，优先只修改其合同文件。只有角色选择、阶段关系或文件归属变化时，才修改本注册表或`orchestration.md`。
6. 完整项目按`orchestration.md`执行“阶段间串行、阶段内按独立性并行”。同阶段并行专家的任务必须包含同一版`work/project_state.md`和已确认上游文件，不得把其他并行专家的未定稿文件加入上下文。
7. 组织与人才配置专家不属于五个市场进入阶段，不得因市场报告完成而自动调用。招聘负责人时读取用户确认的任务受理信息和父任务指定的已有报告，不要求标准项目文件齐全；补齐执行团队时读取`work/project_state.md`和父任务指定的已确认报告。
