# WM Skill

版本 `1.0.2`。WM 取自“外贸”拼音 `Wai Mao` 的两个首字母。仓库根目录保留纯 Skill 源码，WorkBuddy 纯 Skill 与专家版分别打包。

## 下载安装

| 平台与版本 | ZIP 安装包 | 导入对象 |
| --- | --- | --- |
| WorkBuddy 纯 Skill 1.0.2 | [下载 Skill ZIP](https://github.com/yema-code/wm-skill/raw/refs/heads/main/downloads/wm-workbuddy-skill-v1.0.2.zip) | 技能入口；不包含专家配置 |
| WorkBuddy 专家版 1.0.2 | [下载专家 ZIP](https://github.com/yema-code/wm-skill/raw/refs/heads/main/downloads/wm-workbuddy-expert-v1.0.2.zip) | 专家入口；含双语资料、头像、快捷问题和内嵌 WM Skill |
| Codex 1.0.2 | [下载 Codex ZIP](https://github.com/yema-code/wm-skill/raw/refs/heads/main/downloads/wm-codex-v1.0.2.zip) | Codex Skill 目录 |
| SkillHub 1.0.2 | [下载 SkillHub ZIP](https://github.com/yema-code/wm-skill/raw/refs/heads/main/downloads/wm-skillhub-v1.0.2.zip) | SkillHub 分发包 |

请下载对应包，不要把 GitHub 的整个仓库 ZIP 当成专家包。各 ZIP 均有 `wm/` 根目录；专家清单在 `wm/.codebuddy-plugin/plugin.json`，引用 `./skills/wm`。宿主是否直接接受 ZIP 以当前导入界面为准。

## 1.0.2 更新

- 美国获客可选 Google、ImportYeti 或组合流程，CRM 保存来源选择。
- 美洲、欧洲、亚洲大洋洲、中东非洲分地区社区与本地语言查询指导。
- 新增 Zalo、LINE、VK、Telegram、WeChat、KakaoTalk、Viber、Messenger、Instagram DM 九种渠道记录与建联指导。
- CRM 增加国家、语言、业务账号和来源证据字段，兼容旧数据库与 CSV 导出。
- 报告和看板统一作者姓名、邮箱及反馈文案，不写入客户邮件、私信或原始 CRM 数据。
- 专家版补齐双语展示字段、三个快捷问题、头像与技能目录；纯 Skill 包不混入专家配置。

详见 [完整更新说明](RELEASE_NOTES.md) 和 [变更记录](CHANGELOG.md)。这些是流程指导与本地 CRM 能力，不是新增 Google、ImportYeti 或通讯平台 API。

## 能力

- 找客户：市场定位、ICP、查询族、多来源发现、评分和联系人
- 开发信：按客户证据生成首封邮件和三触点跟进序列
- 客户激活：沉默客户识别、激活话术和跟进节奏
- 客户背调：企业身份、贸易信息、合规风险、竞品和社媒核验
- Campaign 与 CRM：分群、抑制规则、本地 SQLite 记录、校验和导出
- TikTok B2B：内容获客、询盘筛选和 CRM 接续 SOP

## 使用

纯 Skill 包按 WorkBuddy 技能导入方式安装；专家包按专家导入方式安装。使用 `@wm`、`/wm` 或 `$wm` 表达任务，实际唤起方式以宿主支持为准。

默认只研究、分析、规划和起草，不自动发送邮件、WhatsApp、LinkedIn 消息或网站表单。真实外联、外部 CRM 写入和自动任务必须由操作者明确授权。

## 资源

详细流程按需读取 `references/`；确定性 CRM 操作使用 `scripts/wm_crm.py`；模板位于 `assets/templates/`。

本次完成了 10 项 CRM 测试、专家字段与目录校验、ZIP 完整性和核心文件一致性检查。尚未在 WorkBuddy 导入界面完成实际运行验收。升级前备份 `.wm/wm.db`；项目与社媒 CSV 新增列，下游请按列名读取。

## 作者与交流

**耶马** · [a1415112688@foxmail.com](mailto:a1415112688@foxmail.com)

欢迎反馈与交流，共建更好的产品体验。免费不易，打赏随缘；如有定制需求，亦可接洽。

![赞赏码](assets/reward-code.png)
