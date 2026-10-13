# Claude / Anthropic Quantumult X 规则

核查日期：2026-10-13。

远程下载 / Quantumult X 订阅地址：

- **完整版（28 条）**：[Anthropic-Full.list](https://raw.githubusercontent.com/tanitany/claude-quantumultx-rules/main/Anthropic-Full.list)
- **专用域名版（10 条）**：[Anthropic.list](https://raw.githubusercontent.com/tanitany/claude-quantumultx-rules/main/Anthropic.list)
- **可选依赖版（18 条）**：[Anthropic-Optional.list](https://raw.githubusercontent.com/tanitany/claude-quantumultx-rules/main/Anthropic-Optional.list)


| 文件 | 启用规则数 | 用途 |
| --- | ---: | --- |
| [Anthropic-Full.list](Anthropic-Full.list) | 28 | 完整版：专用域名及共享依赖 |
| [Anthropic.list](Anthropic.list) | 10 | 专用域名补充版 |
| [Anthropic-Optional.list](Anthropic-Optional.list) | 18 | 共享依赖，可单独选择 |

在 GitHub 打开需要的文件，点击 Raw，复制原始文件地址作为远程规则地址。三种选择为：仅导入完整版；仅导入专用域名版；专用域名版配合可选依赖版。

规则末列使用策略名 `Anthropic`，请映射或替换为实际策略名。完整版包含共享 CDN、Intercom、GitHub、npm 等主机，访问同一主机的其他应用也会命中。

`clau.de` 和 `claudemcpclient.com` 来自社区清单，归属和用途未独立验证。两条遥测规则默认注释。未在实际 Quantumult X 客户端中测试；自定义 MCP、SSO 和其他外部服务可能有额外域名。

见 [核查说明及来源](Anthropic-review.md)。

原始 3 条规则来自 [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script/blob/master/rule/QuantumultX/Anthropic/Anthropic.list)，保留原作者署名；其余为此次核查补充。
