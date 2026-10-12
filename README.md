# clarity · 清晰思考与交付

贯穿理解、分析、执行和回答的通用规范。以第一性原理解释具体问题，直接交付判断和结果，减少防御性转折、空洞对比和程式化附和，让读者抓住重点。

完整规范在 [SKILL.md](SKILL.md)，包含基本原则、工作规则、禁用句式与改法、语义保护和交付前检查。

## 它会怎样改变回答

| 情境 | 原句 | 改写 |
| --- | --- | --- |
| 需要让规则能够指导修改 | 这不是要堆更多规则，而是要让每条规则能指导修改。 | 每条规则都要说明具体怎么改。 |
| 用户只问某组测试是否通过，已知全部通过 | 这组测试通过了，但这并不意味着程序完全没有问题。 | 这组测试已全部通过。 |
| 已知在线版需联网、本地版可离线，用户要兼顾两种环境 | 在线版可以处理文件，但不适用于离线环境。 | 联网时使用在线版，离线时使用本地版。 |

限定语的取舍依据是它是否改变当前判断或行动。改稿保留事实、立场、确定程度和作者有内容的语气。

## 安装到 Codex

个人使用时，安装到用户级技能目录，供各个项目共用：

```sh
mkdir -p ~/.agents/skills
git clone --branch v0.1.0 --depth 1 https://github.com/yuyz-cyber/clarity-skill.git ~/.agents/skills/clarity
```

也可以在 Codex 中调用内置安装技能：

```text
$skill-installer 安装 https://github.com/yuyz-cyber/clarity-skill 的 v0.1.0 版本。技能位于仓库根目录，名称为 clarity，安装到 ~/.agents/skills。
```

安装后，用 `$clarity` 显式调用。Codex 会发现新安装的技能；列表未更新时重启客户端。

希望在日常任务中默认使用时，在个人 `~/.codex/AGENTS.md` 中追加下面的内容，保留文件原有指令：

```markdown
## 清晰思考与交付

处理请求时，读取并遵循 ~/.agents/skills/clarity/SKILL.md 中的 clarity 规范。以用户当前的问题确定分析范围，解释具体机制，直接交付判断和结果。项目专用规则继续按其作用范围生效。
```

个人指令在新会话启动时加载。技能的名称和 description 用于发现与选择；默认使用需要以上加载指令。

团队需要随仓库共享时，将 `SKILL.md`、`LICENSE` 和 `THIRD_PARTY_NOTICES.md` 放入项目的 `.agents/skills/clarity/`，在项目 `AGENTS.md` 中引用该路径。同一环境选择一个安装位置，保持一份规范。

位置和加载方式见 [Codex 技能文档](https://learn.chatgpt.com/docs/build-skills)与 [AGENTS.md 文档](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

## 用于其他 AI

将 [SKILL.md](SKILL.md) 正文加入支持自定义指令的工具，或与具体任务一同提供。加载方式由对应工具配置。

## 初版验证

开发阶段使用独立 agent 比较加载与未加载 skill 的回答，并由不知道组别的 agent 评审。判断与建议题包括日常健康管理、项目学习和习惯调整，共三对首答：加载版两题略优，一题并列。观察到的改善主要是信息顺序和补充内容的相关性；部分回答仍有重复。

该结果来自三个问题、同一默认模型环境，作为初版观察记录。格式校验已通过。

## 参考与许可

参考了以下项目的写作方法、注意力设计和表达约束：

- [shuorenhua](https://github.com/MrGeDiao/shuorenhua)
- [i-have-adhd](https://github.com/ayghri/i-have-adhd)
- [asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill)

本项目采用 [MIT License](LICENSE)。参考项目的版权与许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

