# 分地区社区与通讯渠道开发

用于国家/买家定位、社区检索、关键联系人路由、建联草稿与跟进指导。先确定国家、产品构成和买家类型，再选择发现入口和联系渠道；已有用户选择则直接沿用。

## 按地区读取

仅加载当前任务相关地区。以下研究基于 2026-09-07 的官方公开资料，具体资格、付费功能、活跃度、消息权限及法规在实际使用前复核；“候选/未实测”不升级为已确认能力。

| 地区 | 参考 | 发现与联系重点 |
| --- | --- | --- |
| 美洲 | [regions/americas.md](regions/americas.md) | 美国 Google/ImportYeti 与 HFPA；加拿大 CID；拉美 ConnectAmericas、DENUE、ABUP 等 |
| 欧洲及俄罗斯 | [regions/europe.md](regions/europe.md) | EEN Business request、wlw/Europages、家纺展会；LinkedIn，按目标企业检查 VK/Telegram |
| 亚洲及大洋洲 | [regions/asia.md](regions/asia.md) | 当地目录/协会、NAVER Cafe、LINE OpenChat；Zalo、LINE、KakaoTalk、WeChat 等 |
| 中东与非洲 | [regions/africa-middleeast.md](regions/africa-middleeast.md) | TEXMAS、酒店协会、当地商会/目录与展会，英语/法语/阿语按国家选择 |

不要求每个国家有独立 App。行业协会、展会配对和跨国平台中的本地社区可能更接近真实买方。国家普及率不能代替企业实际业务入口。

## 查询到客户开发

1. 定客户角色：进口分销、自有品牌/零售、酒店/项目采购分开；家纺先确认套件组成、当地尺寸与真实供货能力。
2. 选来源：区分采购需求、供应商目录、行业社区、职业/内容平台、通讯工具。目录中的制造商先判为供给侧，进口经销/贴牌品牌经证据支持后才视为潜在买方。
3. 生成查询：产品 + 当地角色词 + 应用 + 城市；再找采购、品类、供应链和项目负责人。平台内不一定支持 Google 的 `site:` 或 OR 语法。
4. 审核社区：管理员/组织身份、广告规则、最近讨论、买方密度、公开性。群人数/订阅数不证明采购需求；禁止广告的群只在允许范围内研究。
5. 核验公司及人员：官网、注册/行业资料、官方账号与职业身份交叉核对；无个人联系入口时用企业采购入口，不猜私人账号或手机号。
6. 设计首次联系：基于一个真实业务观察，确认采购职责或请求提供一页资料；得到回应后再核规格、采购方式、时间和样品标准。
7. 分层背调：初筛核实体与业务；建联前核角色/路由/联系依据；交易前核合同、收款、进口资格、履约及风险。登记正常不等于信用可靠。
8. 跟进：资料评审 → 样品 → 反馈 → 报价/小单 → 复购，每步记录负责人和下一日期；明确拒绝或退出时停止，不换平台追发。

## 平台边界与建联动作

| 平台 | 搜索/使用方式 | 重要限制 |
| --- | --- | --- |
| LinkedIn | 已知公司 → 当前职能/职位 → 公开职业证据 → 相关的业务联系草稿 | 高级筛选依套餐；个人主页不自动证明采购权 |
| Facebook / Messenger | 按国家、经营场景与本地语言找行业群和企业 Page；Messenger 承接业务对话 | 入群不是营销许可，不能批量私信群成员 |
| Instagram / Instagram DM | 从品牌、地点、行业活动与官网反链识别企业；DM 先确认业务职责 | 粉丝与评论者不是采购名单；DM 和账号观察分别记录 |
| Zalo | 越南企业官网/官方页面确认 OA、业务 ID 或二维码 | OA 双向消息面向曾互动客户，不是陌生采购经理库 |
| LINE | OpenChat 用于公开行业话题；OA 用于企业客户沟通 | OA 与 OpenChat 不同，好友/地区/账号条件需要核实 |
| KakaoTalk | 韩国企业官网确认 Channel，使用公开的企业咨询入口 | Channel 客服不是采购经理；规范枚举为 `kakaotalk` |
| WeChat | 公司公开业务 ID/二维码、真实商会或展会引荐 | 无公开群数据库承诺，不通过手机号猜账号 |
| VK | 先由本地企业官网核验企业社区，再研究公开业务内容 | 具体内部搜索和消息界面本次未实测，遇登录限制如实说明 |
| Telegram | 公开用户名、企业 t.me 链接、行业群/频道说明 | 频道是广播，不是买家成员表；私密内容不假定可见 |
| Viber | 企业提供的业务入口或公开社区，按允许方式参与 | 社区隐藏成员电话，不承诺取得号码 |
| WhatsApp | 已核验的企业路由与接收方许可，用于规格/样品跟进 | 官方 Business 政策要求号码与 opt-in，公开号码本身不足 |

## CRM 与证据

- 社媒企业主账号用 `upsert-social`；`country`、`language`、`source_url` 和 `last_checked_at` 保存国家、语言、归属来源与观察日。只有官方公布的业务 ID 时用 `public_handle`，不编造 `profile_url`。
- `social_profiles` 仍是“实体 + 平台”的一个主账号，不覆盖已有关键联系人来塞多个个人账号。多个采购角色用独立 `contacts`，个人公开业务渠道作为该联系人的 `profile_url` 或字段级 `evidence`，再按 `contact_id` 建外联/激活计划。
- `instagram` 记录账号观察，`instagram_dm` 记录 DM 渠道；输入别名或 Kakotalk 拼写先解释并规范化为平台枚举。当前脚本不自动识别全部别名。
- 账号归属、角色、需求与联系许可分开陈述。许可来源/范围、拒收或未确认状态记录于计划 `notes`/证据，不能把 `official_linked` 写成允许营销。
- 不自动入群、加好友、发送邮件/DM、申请采购公告或付费。Skill 提供研究计划、数据操作、草稿和操作者下一步指导。

## 共同官方依据

访问日期 2026-09-07：[WhatsApp Business](https://business.whatsapp.com/policy)、[Viber Communities](https://www.viber.com/communities/)、[Telegram FAQ](https://telegram.org/faq)、[LinkedIn Sales Navigator](https://business.linkedin.com/sales-solutions/sales-navigator)、[Meta Spam 规则](https://transparency.meta.com/policies/community-standards/spam/)。国别来源及未核实范围见上方四份地区参考。
