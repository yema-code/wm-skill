# 美国市场获客来源选择

美国找客户时使用；其他国家按 [global-messaging.md](global-messaging.md) 选择当地入口。这里定义研究和人工操作流程，不提供 Google/ImportYeti 自动接口，也不代为购买数据或发送消息。

## 操作者选择

用户已指定来源则直接使用；未指定时问一个问题：“这次用 Google、ImportYeti，还是两者组合？”不要把自己建议的组合写成用户已选。

| 选择 | 项目 lead_sources | 适用方式 |
| --- | --- | --- |
| Google | `["google"]` | 找当前经营相关产品的品牌、进口商、分销商和酒店供应渠道 |
| ImportYeti | `["importyeti"]` | 以贸易关系发现候选；仍须到官网/注册及职业来源核验 |
| 组合 | `["google","importyeti"]` | 官网发现与交易线索交叉核对，按公司实体去重 |

选定后通过 `set-project` 保存 `lead_sources`、`source_selection: "operator_choice"`；`source_notes` 记录所选数据集、时间范围、访问条件及限制。尚未选择时保持空数组与 `pending`。不因恢复项目而反复询问已保存的选择。

## Google 查询

将产品组成、买家角色、应用、地理和业务词组合，按任务取用：

```text
"duvet cover sets" (importer OR distributor) "United States"
"bed linen" "private label" retailer
"hospitality linen" wholesaler "California"
"Company Name" (procurement OR sourcing OR "supplier registration")
```

`.com` 不是美国筛选条件，需核对经营地址和服务市场。四件套必须先明确 sheet set / duvet cover set / comforter set 的组成，酒店布草不默认按零售四件套采购。搜索摘要只发现入口，不代替原页证据。

## ImportYeti 流程

1. 先确认当前账号能访问的数据集、筛选项和时间范围；不假定所有套餐都支持产品描述、HS 或完整导出。
2. 以已知进口商、供应商/品牌名或页面实际支持的产品查询方式发现企业。未访问原页时保留为待核验。
3. 记录公司/交易对手、产品描述、最近交易日期、观察日期、原始 URL、记录数量和计量口径。提单数、箱数、重量不是同一指标，更不能推算为准确采购金额。
4. 区分进口主体、收货人、通知方、货代、报关行、品牌和集团。不能确认实际买方时进入 `review`；没有官网的候选先保存在项目研究记录，不编造域名写入 CRM。
5. 回公司官网核验产品、国家、商业模式及采购入口，再用公开职业资料定位采购/品类/供应链负责人。
6. 与 Google 结果按规范化官网域名合并，交易证据和官网证据分别保留。来源冲突时两条都保存并说明未知项，不选择性删掉冲突。

贸易历史不证明当前采购意向、预算、信用或愿意接受推销；未检索到记录也不能证明没有进口。遇登录、验证或付费限制时停止该入口，说明限制并提供可用的研究替代，不能声称已拿到未读取数据。

## 记录与交付

使用 `assets/templates/discovery-log.json` 保存每轮查询和候选观察，作为项目侧研究日志；它不是 CRM 导入命令的输入。日志保存 `discovery_source`、`source_query`、`source_url`、`observed_at`、`verification_status`、贸易信号及下一验证动作。

已确认官网的公司按现有 `upsert-company` 保存；原始贸易主张通过 `add-evidence` 保存为 `source_type: "trade_source"`，官网验证保存为 `official`。查询页留在研究日志，不充当原始主张证据。下一步交付公司证据、未知项、角色与建议渠道，不交付虚构联系方式。

## 数据范围与来源

2026-09-07 阅读 [ImportYeti 官方 FAQ](https://www.importyeti.com/faqs#/article/faq-011)：美国海运进口主要来自 CBP 提单，另说明美国出口、通关及墨西哥数据集。不要写成全站只含海运，也不要声称覆盖整个北美或全部运输记录；运行时核对具体数据集。

加拿大可评估 [Canadian Importers Database](https://ised-isde.canada.ca/site/canadian-importers-database/en)，保存来源值 `canadian_importers_database`。本次官方页基于 2023 数据，包含报关代理与非居民进口商，不能当实时完整买家名单。更多国别来源见 [regions/americas.md](regions/americas.md)。
