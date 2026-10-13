核查日期：2026 年 10 月 13 日。

原列表不完整。取回的原文件只有 3 条规则，标注更新时间为 2024-01-08 16:02:59。
补充版 Anthropic.list 保留原 3 条，新增 7 条，共 10 条。其中 5 条有官方页面依据，2 条来自社区维护列表，证据等级已在规则中注明。

| 新增后缀 | 依据及用途 |
| --- | --- |
| claude.com | 官方网络文档列出；覆盖登录入口、platform 控制台、code 文档、support 帮助中心、academy 等子域名。 |
| claude.app | 官方桌面网络文档列出，包含动态 livepreview 子域名。 |
| claudeusercontent.com | 官方网络文档列出；包含 Artifacts 内容及 bridge.claudeusercontent.com。 |
| claudemcpcontent.com | 官方文档说明 MCP 交互组件使用其动态子域名。 |
| claude.dev | Claude 官方首页直接链接的开发者博客；独立域名需单独分流。 |
| clau.de | v2fly 的 Anthropic 分类收录。未在本次核查的官方网络文档中找到；直接访问返回 403，未独立确认归属与具体用途。 |
| claudemcpclient.com | v2fly 的 Anthropic 分类收录。未在本次核查的官方网络文档中找到；直接访问发生 TLS 错误，未独立确认归属与具体用途。 |

原后缀规则已覆盖以下例子，无需重复列出：

- anthropic.com：api、a-api、a-cdn、s-cdn、assets-proxy、mcp-proxy、status、trust 等子域名。
- claude.ai：a、assets、downloads，以及动态 livepreview 子域名。

新增的 claude.com 后缀规则也覆盖 platform.claude.com、code.claude.com、docs.claude.com、support.claude.com、assets.claude.com 和 academy.claude.com。
动态内容域名使用 HOST-SUFFIX 覆盖，规则中无需写星号。

Anthropic-Optional.list 包含 18 条默认启用的精确主机规则：7 个 Artifacts 字体与脚本库主机、4 个帮助中心依赖、2 个企业官网资源主机、5 个 Claude Code 条件依赖。
另外保留 2 条已注释的遥测规则，不计入 18 条。

| 可选范围 | 说明 |
| --- | --- |
| Artifacts | 官方列出的 Google Fonts 和 5 个脚本库主机。字体不可达可退回默认字体；脚本库不可达可能导致对应组件无法运行。 |
| 帮助中心 | 从 support.claude.com 官方 HTML 的资源地址及配置读取 Intercom 依赖；仅代表此次页面观测。 |
| 企业官网 | 从 www.anthropic.com 官方 HTML 读取 Webflow 资源主机；不代表这些资源是 Claude 对话服务的必要依赖。 |
| Claude Code | 官方文档列出的对象存储、npm、GitHub、更新日志和 Homebrew 检查；是否访问取决于安装方式及插件等功能。 |
| 遥测 | 官方文档列出的 2 个可选 Datadog 接收主机，规则默认注释。 |

启用可选规则后，其他网站访问这些相同主机也会命中 Anthropic 策略。仅凭域名，Quantumult X 无法把同一共享主机上的 Claude 请求与其他请求区分开。
因此没有对 googleapis.com、cloudflare.com、cloudfront.net、githubusercontent.com 等共享根域名做整域分流。

使用方式：用 Anthropic.list 替换原规则内容；也可以仅将新增 7 条追加到本地规则。
文件末列保留原策略名 Anthropic，如现有策略名称不同，需要替换成实际名称。
按需导入 Anthropic-Optional.list，或从中挑选所需条目。
上游 blackmatrix7/ios_rule_script 仓库没有被修改；本补充发布到独立仓库。继续订阅上游原 URL 不会自动获得这些补充。
规则顺序与现有配置的 policy 参数可能影响最终策略，以 Quantumult X 请求记录中的命中规则为准。

核查范围与限制：

- 核对原规则、官方桌面/CLI 网络文档、Claude 官网链接、官方帮助中心及企业官网 HTML，并交叉检查 v2fly 列表。
- 已验证规则字段、计数、重复项和官方专用域名示例的覆盖关系；没有在实际 Quantumult X 客户端中导入测试，也没有进行登录后全流程抓包。
- 用户自行连接的 MCP 服务、企业 SSO、支付或第三方登录跳转、Claude Code 自行访问的网站，以及 Bedrock 等其他提供方均可能有额外域名。这些无法由固定的 Claude 专用规则全部枚举。
- 官方清单、网页依赖和社区条目可能变化。本结果是本次核查的补充，不保证覆盖所有账号、地区和操作下的全部网络请求。

来源（可在浏览器中打开）：

```text
原规则
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/Anthropic/Anthropic.list

官方桌面网络要求
https://code.claude.com/docs/en/desktop#network-access-requirements

官方 CLI 网络要求与第三方依赖
https://code.claude.com/docs/en/network-config

官方首页及开发者博客
https://claude.com/
https://claude.dev/

官方帮助中心和企业官网（HTML 资源检查）
https://support.claude.com/en/
https://www.anthropic.com/

社区维护列表（仅用作社区条目依据）
https://raw.githubusercontent.com/v2fly/domain-list-community/master/data/anthropic

Quantumult X 官方配置样例
https://raw.githubusercontent.com/crossutility/Quantumult-X/master/sample.conf
```

完整版：Anthropic-Full.list 合并主规则与可选依赖，共 28 条启用规则（19 条 HOST、9 条 HOST-SUFFIX）；2 条遥测规则继续保持注释。完整版会同时分流共享依赖主机上的其他流量。

发布仓库：https://github.com/tanitany/claude-quantumultx-rules

完整版原始下载地址：https://raw.githubusercontent.com/tanitany/claude-quantumultx-rules/main/Anthropic-Full.list
