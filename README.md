# PLC 编程学习 AI 教练 · plc-programming-ai-tutor

A one-on-one PLC programming coach for Siemens TIA Portal. It does not teach by lecturing — it hands out **one 20–40 minute task at a time**, grades your work against **pass/fail criteria backed by evidence**, and when you are stuck it gives **the smallest useful hint instead of the answer**.

西门子 PLC 编程的一对一训练技能（博途 / TIA Portal，IEC 61131 通用）。

## 它和"看教程"的区别

| | 看教程 | 这个技能 |
|---|---|---|
| 谁决定进度 | 视频/文章的目录 | 你的判分结果 |
| 教材 | 别人的例子 | 你自己的工程（或最小练习） |
| 怎么算学会 | 看完 | 判据 PASS，且有证据 |
| 卡住了 | 倒回去重看 | 三级提示，每级都要你再试一次 |

## 它怎么工作

```
读进度 → 三问诊断 → 定一个 checkpoint → 出题（交付物 + 判据）
  → 你做 → 按证据判 PASS/FAIL → 一级提示 → 记账 → 收尾
```

- **判分只认四种证据**：编译输出原文、用例 PASS/FAIL、从工程读回的对象、你贴出的原始报错。"应该能跑"不算。
- **不代写**：卡住给三级提示（方向 → 定位 → 改法），三级不过就回退一层。你要答案可以给，但记 `PASS(抄)`，下次换同类型题重做。
- **有进度**：`learn-progress.md` 写在你工程目录旁，下次会话接着走。

## 六层 · 15 个 checkpoint

| 层 | 在练什么 | 怎么算学会了 |
|---|---|---|
| L0 环境与基线 | 能编译、能跑一个最小块 | 起保停编译 0 错误 0 警告 |
| L1 读图 | 看懂别人画的逻辑 | 复述一段 5 网络梯形图 |
| L2 写块 | 从需求写到能编译 | 互锁、定时器、边沿、状态机 |
| L3 验证 | 证明它对 | 用例表 + 时序核对 |
| L4 读老工程 | 把陌生工程变可读 | 改一个 IO 能列出受影响的块 |
| L5 改造与交付 | 改得动、交得出 | 加功能不破坏、重构不改变行为 |

每个 checkpoint 都有一页**手把手**：点击级步骤、可照抄的写法、常见报错、三个"为什么"（PASS 之后才讲）。共 17 页，见 `references/handbook/`。

## 安装

```bash
npx skills add tia-forge/plc-programming-ai-tutor
```

其他渠道：

| 客户端 | 怎么装 |
|---|---|
| WorkBuddy / CodeBuddy | 插件页 → 添加第三方市场 → `https://raw.githubusercontent.com/tia-forge/tiaforge-plugins/main/.codebuddy-plugin/marketplace.json` → 装 `tiaforge`（一次带齐 6 个技能） |
| DeepSeek Harness | `dsh plugin --profile web add dsh-tiaforge` |
| SkillHub | 搜「PLC 编程学习 AI 教练」 |
| pi | `pi install npm:pi-tiaforge` |

## 三种练法

| 你的条件 | 怎么练 |
|---|---|
| 有博途 + TiaLink | 用你自己的工程当教材：读工程、建块、编译、读回、下载仿真 |
| 有博途，没 TiaLink | 手敲手编译，把编译输出贴回来，照样判分 |
| 没博途 | 给 SCL 文本，云端仿真跑用例拿 PASS/FAIL；梯形图用生成 + 渲染成图对照 |

**没装博途也能走完 L0–L3**；L4（读老工程）必须有真工程——这一层存在的意义就是"你手上那套工程"。

## 边界

- 不替你写完整答案（默认只给提示与判据）。
- 不承诺一次通过。产出不是"AI 一次写对"，是"错在第几轮被发现"。
- 不碰安全功能：急停、安全门、光幕、超压走安全继电器或安全 PLC。
- 不替代师傅和现场：它管"这段逻辑对不对、凭什么"，不管"这台机器该不该这么设计"。

## 相关技能（都可选）

`tialink-tia-portal`（真工程里编译/下载/读回）、`plc-cloud-sim`（不装博途跑用例）、`tia-portal-docs`（指令参数与版本行为）、`laddoc-cloud` + `lad-render-cloud`（梯形图生成与看图）、`plc-program-design`（做完整项目时的五张表）。

## License

CC BY 4.0
