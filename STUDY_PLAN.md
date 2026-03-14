# 题海战术升级：从“刷题”到“知识图谱”

这份文档用于把每道题沉淀成可复用的知识资产，避免只记答案、很快遗忘。

## 1) 先解你这道题（示例）

题目：获取 `input` 节点的正确方法。

```html
<form class="file" name="upload">
  <input id="file" name="file" />
</form>
```

选项判断：

- A `document.querySelectorAll('file')[0]` ❌：`'file'` 会匹配 `<file>` 标签，不是 `id="file"`。
- B `document.getElementById('file')[0]` ❌：`getElementById` 返回单个元素或 `null`，不能再 `[0]`。
- C `document.getElementByTagName('file')[0]` ❌：API 名字就错了，正确是 `getElementsByTagName`；且 `'file'` 不是标签名。
- D `document.getElementById('file')` ✅：正确。

可补充正确写法：

```js
const input1 = document.getElementById('file')
const input2 = document.querySelector('#file')
```

---

## 2) 每道题都按 4 步沉淀

> 目标：一道题至少产出 1 个知识点 + 1 个定位 + 1 个易错点。

1. **题目结论**：正确答案 + 为什么。
2. **知识点定义**：一句话解释“本质规则”。
3. **全局位置**：它在前端知识体系里的层级位置。
4. **迁移练习**：再造 1~2 个变体题，确认会用。

---

## 3) 知识点“全局位置”怎么写

建议固定格式：

- 领域：Web 前端
- 一级：JavaScript / DOM
- 二级：DOM 查询 API
- 三级：按 ID 查询（`getElementById`）
- 相关：`querySelector`、`querySelectorAll`、`getElementsByTagName`
- 常见陷阱：返回值类型（单节点 vs 节点列表）

---

## 4) 刷题不无聊的关键：改成“任务流”

把“做题”变成有产出的项目：

- **任务 A（做题）**：每天 20 题。
- **任务 B（归档）**：把错题写入 `notes/questions/`。
- **任务 C（建图）**：每晚把新知识点挂到 `notes/map.md`。
- **任务 D（复盘）**：每周整理“最高频 10 个坑”。

这样你每天会有“可见进展”（文档越来越完整），不只是做完就忘。

---

## 5) 建议的仓库结构（可直接用）

```txt
.
├─ README.md
├─ notes/
│  ├─ map.md                 # 全局知识地图
│  ├─ pitfalls.md            # 高频易错点
│  └─ questions/
│     ├─ 2026-03-14-q001.md
│     └─ 2026-03-14-q002.md
└─ templates/
   └─ question-template.md   # 单题模板
```

---

## 6) 单题模板

复制到 `templates/question-template.md` 使用。

```md
# Qxxx 标题

## 题目
- 来源：
- 题干：
- 选项：

## 我的答案
- 选择：
- 结果：对 / 错

## 正确解析
- 正确答案：
- 关键原因：

## 知识点
- 名称：
- 一句话定义：
- 全局位置：领域 > 一级 > 二级 > 三级
- 关联概念：

## 易错点
- 我为什么会错：
- 以后如何避免：

## 迁移练习
- 变体题 1：
- 变体题 2：
```

---

## 7) 你担心“上下文丢失”，怎么解

你的思路是对的：把长期内容放进项目，而不是只靠聊天上下文。

推荐实践：

1. 用仓库保存知识库（题目解析、地图、错因）。
2. 每次新题都按模板写，模型只需要基于仓库继续补充。
3. 每周让模型做一次“总复盘”：
   - 哪些知识点反复错？
   - 哪些是“概念不清”而不是“粗心”？
   - 下周优先级怎么排？

---

## 8) 7 天启动版（轻量）

- Day 1：建目录 + 模板 + 录入 20 题。
- Day 2~6：每天 20 题，至少沉淀 5 条知识点。
- Day 7：输出一份周报：
  - 总题数
  - 错题率
  - Top 10 易错点
  - 下周学习计划

> 先跑起来，比“完美系统”更重要。
