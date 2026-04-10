# 风鸟企业查询 Skill · Fengniao Company Search

> 一个面向 Claude Code 的中国企业信息查询 Skill，覆盖工商、股权、司法、风险等核心维度。适合企业尽调、合作方背景调查、供应商准入等场景，也是企查查 / 天眼查 / 爱企查的 AI 原生平替。

## 能力覆盖

| 维度 | 说明 |
|------|------|
| 企业基本信息 | 法人、注册资本、成立日期、统一社会信用代码、注册地址、经营范围 |
| 股东信息 | 股权结构、出资比例 |
| 高级职员 | 董事、监事、高管、法定代表人 |
| 对外投资 | 该企业对外参股/控股的企业列表 |
| 工商变更 | 历史变更记录 |
| 被执行人 | 法院强制执行记录 |
| 失信被执行人 | 老赖名单 |
| 限制高消费 | 限高令记录 |
| 经营异常 | 工商列入异常经营名录记录 |
| 严重违法 | 工商列入严重违法失信名单记录 |
| 行政处罚 | 各类行政执法处罚记录 |
| 企业尽调报告 | 整合以上维度，一键生成结构化尽调摘要 |

## 快速开始

### 前置条件

- Node.js 18+
- **无需配置 API Key**，内置公用 Key 开箱即用（每日 1000 次）

### 安装

按照 Claude Code Skill 标准安装方式安装本 skill 后，直接对话即可触发：

```
我要跟这家公司签合同，先查一下对方背景和风险
这家供应商靠谱吗，帮我做个企业风险筛查
帮我查一下比亚迪的股东和对外投资
信数科技的法人是谁
雷军名下有哪些公司
帮我查一下这家公司有没有被执行记录
```

### 本地验证

```bash
# 1. 发现工具（无需联网）
node scripts/tool.mjs discover "企业基本信息"

# 2. 模糊搜索企业，获取 entid
node scripts/tool.mjs call biz_fuzzy_search --params '{"key":"腾讯"}'

# 3. 用 entid 查询具体维度
node scripts/tool.mjs call biz_basic_info --params '{"entid":"AerjZTfkSh0"}'
```

## 使用私有 API Key（可选）

如果你有自己的风鸟付费账号，可配置私有 Key，优先级高于内置公用 Key：

```bash
# macOS / Linux
export FN_API_KEY="你的API Key"

# Windows PowerShell
$env:FN_API_KEY = "你的API Key"
```

公用 Key 剩余额度实时查询：https://www.riskbird.com/skills

## 数据来源

数据由 **风鸟（Riskbird / 美亚风鸟）** 提供，官网：https://www.riskbird.com

## License

MIT
