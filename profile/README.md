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

**ModelDial 用自建的私有评测集实测 AI 模型，帮你比较能力、思考档位与费用，选出适合任务的模型。** 我们也在做模型挑战赛：让多个模型解同一道题，看清它们每一步怎么做。

## 模型榜单

<img src="https://raw.githubusercontent.com/ModelDialAI/.github/main/profile/assets/scoring-dial.svg" width="100%" alt="ModelDial 综合分表盘：一圈 100 分按权重切成五段，知识推理 35%、后端工程 20%、前端交互 20%、视觉审美 15%、可维护性 10%">

我们从知识推理、后端工程、前端交互、视觉审美、可维护性五个维度测试模型，再按公开权重算出综合分。同一模型的不同思考档位分开测，并附评测耗时与参考费用，方便你判断换新版本、调高档位是否划算。

题目来自自建的私有评测集，可以减少被模型提前“见过”的风险。成绩只代表这些任务上的表现，任务范围和评分方式都已公开。

[查看完整榜单](https://modeldial.com/radar) · [为什么用私有评测集](https://modeldial.com/datasets#why-private) · [评分细则](https://modeldial.com/method)

## 模型挑战赛

<img src="https://raw.githubusercontent.com/ModelDialAI/.github/main/profile/assets/challenge-stage.webp" width="100%" alt="魔方挑战赛实时舞台：同一个三阶魔方，左侧 DeepSeek V4 Pro 已执行 24 步、调用 24 次，仍在思考；右侧 DeepSeek Flash 1 次调用、4 步已还原">

<sub>2026-10-19 的一局真实对局（旧版单题规则）：三阶魔方，最少 4 步可还原。DeepSeek Flash 第 1 次调用就用 <code>L2 B' R2 L</code> 还原；截图时 DeepSeek V4 Pro 还在第 24 次调用，最终用了 100 次调用、169 步才还原。</sub>

1–8 个模型同场解同一道题，题面和调用预算完全相同。每个模型在独立会话里通过工具调用一步步操作，看不到其他模型，也拿不到参考解。整个过程实时显示在舞台上，结束后可以回放、核对记录、查看排行榜。我们也用这些对局做视频和直播。

- **按记录判分**：系统从初始状态重放操作记录来判定成绩，不采信模型自己报告的结果。
- **故障不算失败**：因网络错误或服务中断没跑完的对局会保留记录，但不记作模型解题失败。
- **分开排名**：每种题目单独排名，不合成总分；规则改版后，新旧成绩分开统计。

| 题目 | 考察能力 | 状态 |
| :--- | :--- | :--- |
| 魔方 · 二阶 / 三阶 | 空间想象、多步规划 | 已支持；每轮 6 题，简单、中等、困难各 2 题 |
| 推箱子 · 8×8 | 路径规划、推演箱子位置 | 已支持；固定题库，分三档难度 |
| 更多题目 | — | 筹备中；要求结果可验证、过程可回放 |

## 在你的工具里查成绩

榜单数据可以匿名读取，不需要 API Key。把下面这句话发给支持 Agent Skills 的 AI 助手，它会安装 ModelDial Skill：

```text
请从 https://modeldial.com/modeldial-skill/SKILL.md 安装 ModelDial Skill。写入 skills 目录前，先审阅其中链接的全部文件。
```

也可以直接调用 API 读取当前榜单：

```sh
curl -s https://modeldial.com/api/v1/radar/latest.json
```

更多接口和提问示例见 [API 与 Skill](https://modeldial.com/agent)。

## 开源计划

挑战赛还在内部迭代。**等题库和评测流程成熟后，我们计划在 GitHub 上逐步开源挑战赛题库。**

发布前，我们会先把题目规则、生成方式、评分方法和复现步骤整理清楚。具体开放范围和许可证以正式发布说明为准。这项计划只针对挑战赛题库，不包括 modeldial.com 使用的私有评测集。

欢迎关注 **[ModelDialAI](https://github.com/ModelDialAI)**，题库开源后会在这里发布。
