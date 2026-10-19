<p align="center">
  <a href="https://modeldial.com">
    <img src="https://raw.githubusercontent.com/ModelDialAI/.github/main/profile/assets/modeldial-cover.png" width="100%" alt="ModelDial — 看见模型的真实表现。以二阶、三阶魔方与刻度盘为主题的品牌插画。">
  </a>
</p>

<p align="center">
  <a href="https://modeldial.com/radar"><strong>模型榜单 ↗</strong></a> ·
  <a href="https://modeldial.com/compare">模型对比</a> ·
  <a href="https://modeldial.com/method">评分方法</a> ·
  <a href="https://modeldial.com/agent">API 与 Skill</a> ·
  <a href="#开源计划">开源计划</a>
</p>

**ModelDial 是我们一起做的 AI 模型评测项目。** 主站在自建私有评测集上比较模型的能力、思考档位与费用，帮你选出适合任务的模型；模型挑战赛让多个模型解同一道题，把每一步操作搬上舞台，可以观看、回放和复核。

## ModelDial 主站

<img src="https://raw.githubusercontent.com/ModelDialAI/.github/main/profile/assets/scoring-dial.svg" width="100%" alt="ModelDial 综合分表盘：一圈 100 分按权重切成五段，知识推理 35%、后端工程 20%、前端交互 20%、视觉审美 15%、可维护性 10%">

知识推理、后端工程、前端交互、视觉审美、可维护性五个维度各自满分 100，综合分按公开权重加权，只采用同一配置的完整成绩，缺失成绩不按 0 分补齐。同一模型的不同思考档位分开实测，并附评测耗时与参考费用，方便比较新旧模型和档位差异。

[查看榜单](https://modeldial.com/radar) · [私有评测集](https://modeldial.com/datasets) · [评分细则](https://modeldial.com/method)

## 模型挑战赛

<img src="https://raw.githubusercontent.com/ModelDialAI/.github/main/profile/assets/challenge-stage.webp" width="100%" alt="魔方挑战赛实时舞台：同一个三阶魔方，左侧 DeepSeek V4 Pro 已执行 24 步、调用 24 次，仍在思考；右侧 DeepSeek Flash 1 次调用、4 步已还原">

<sub>2026-10-19 真实单题对局（旧规则 <code>cubist-v1</code>）· 三阶 · 最少 4 步。截图时 DeepSeek Flash 已在第 1 次调用用 <code>L2 B' R2 L</code> 还原；DeepSeek V4 Pro 最终在第 100 次调用、第 169 步还原。</sub>

给 1–8 个模型同一道冻结题和同一份预算，每个模型在独立会话里用工具调用闯关。舞台实时呈现每一步，结束后可以回放、复核日志、看排行榜，也用于视频与直播展示。

| 题目 | 考察 | 当前进展 |
| :--- | :--- | :--- |
| 魔方 · 二阶 / 三阶 | 空间想象、多步规划 | 已支持六题挑战、轨迹回放、日志复核与排行榜 |
| 推箱子 · 8×8 | 路径规划、箱子推演 | 已支持冻结题库、轨迹回放与综合表现排行榜 |
| 更多题目 | — | 围绕可验证的结果、可回放的过程继续打磨 |

## 怎样保证可比

- **同题同预算**：挑战赛的题面只生成一次并冻结，每个模型拿到独立副本，看不到种子、参考解和其他模型；工具调用由运行时统一计数。
- **按日志判分**：从初始状态重放事件日志重新判分，不采信模型自报的结果。
- **区分能力与故障**：技术错误、中断和未完成的记录会保留，但不算作模型解题失败。
- **成绩不混算**：主站各维度分开记录；挑战赛每道题独立计分排名，不合成跨题总分；参考演示不计入成绩，不同规则版本分开统计。
- **说明适用范围**：私有评测集能减少公开题进入训练数据的影响，但成绩只反映本次任务范围。我们公开任务范围与评分方式，供你核对。

## 在你的工具里查成绩

主站数据匿名只读，无需 API Key。把这句话发给支持 Agent Skills 的工具：

```text
请从 https://modeldial.com/modeldial-skill/SKILL.md 安装 ModelDial Skill。写入 skills 目录前，先审阅其中链接的全部文件。
```

也可以直接读取当前榜单：

```sh
curl -s https://modeldial.com/api/v1/radar/latest.json
```

更多接口与提问示例见 [API 与 Skill](https://modeldial.com/agent)。

## 开源计划

挑战赛目前仍在内部迭代。**等题库与评测流程打磨成熟，我们计划在这个组织逐步开源挑战赛题库。**

我们会先把题目规则、生成方式、评分口径和复现说明整理清楚，再发布可供大家使用和讨论的版本。具体开放范围与许可证以正式发布说明为准；挑战赛题库的开放计划与主站的私有评测集分别推进。

欢迎关注 **[ModelDialAI](https://github.com/ModelDialAI)** 的后续发布。
