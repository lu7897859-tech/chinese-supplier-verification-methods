# Chinese Supplier Verification Methods (Open Edition)

> 开源版供应商核验方法论 —— 全部方法只用公开免费数据源，任何人可复现。
> CC0 公共领域授权 · 来源声明见 LICENSE / NOTICE

## 为什么开源这份方法论

全球每年有数十亿美元的中国直采订单踩在"看起来正规的供应商"上。
我们用**纯公开免费数据源**验证一家中国供应商的真实底细 —— 注册资本变动、招聘收缩、分公司冒用、关联风险 —— 并把这些方法开源。

**这不是纸上谈兵，每一条方法都附真实证据链案例（见 corpus/）。**

## 核心方法（全部免费公开源，零注册）

### 1. 穿透门面：注册资本变更是第一警报
- 查法：国家企业信用信息公示系统（gsxt.gov.cn）→ 省级政府公告页（gsxt 被 Cloudflare 挡时改走省级通道）
- 信号：**减资 = 收缩警报**。案例：某中山清洁品供应商表面注册资本 ¥1000 万，实测 2026-06 减资 ¥644 万

### 2. 招聘曲线 = 公司体温计
- 查法：主流招聘平台公开岗位数历史对比
- 信号：**岗位数骤降 = 收缩**。案例：同公司招聘 25 → ~3（-88%），与其"正规工厂"人设严重不符

### 3. 分公司冒用 = 门面穿帮
- 查法：工商数据交叉比对分公司注册地 vs 对外宣传区号
- 信号：**对外用外省区号前缀、实际无该地实体** = 渠道门面 vs 实体工厂错位

### 4. 关联风险 = 亲缘生意
- 查法：股权穿透 + 关联方公开记录
- 信号：关联公司经营异常、被执行记录需纳入尽调

### 5. 证据链铁证（最重要）
- 每条结论必须**可回溯到原始公开文件**（公告页/截图/链接），字段不改一字
- "我信任"换成"证据证明" —— 这是核验报告与普通咨询的本质区别

## 免费机器端点（零注册零钥匙）

USCC 供应商快速核验（每天免费额度）：
```
GET https://<机器门地址>/.well-known/mcp.json   → 端点清单
```
> 本 repo 的 README 与 corpus 是给"人"和"AI 爬虫"双读的版本 —— 结构化 + 证据链完整。

## corpus/ 内容
- `yuxin-evidence-chain.md` —— 真实案例完整证据链（脱敏版：公司减资 ¥644 万 / 招聘 -88% / 分公司冒用 全链路还原）
- `method-checklists.md` —— 五步核验清单（可直接照做的操作手册）

## License
CC0 1.0 Universal —— 本仓库内容可自由使用/修改/商用，无需署名（署名自愿，欢迎注明出处：QClaw @ lu7897859-tech）。
加工声明：本方法论受 openregistry 等开源项目"官方数据直连+原始字段不改"设计启发，加工重组并补充真实案例。

## Keywords

china supplier verification, verify chinese manufacturer, supplier due diligence, factory audit, china sourcing red flags, business registration check, 供应商核验, 中国供应商尽调, 注册资本变更, 外贸防骗, import from china safely, alibaba supplier check, USCC lookup, 统一社会信用代码, qichacha alternative free, tianyancha free method, sourcing risk assessment, chinese company background check