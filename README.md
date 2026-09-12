# PR Content Collaboration Brief Generator

将新闻稿、产品发布信息和案例素材，整理成面向媒体机构或新媒体博主的内容合作 Brief。

A reusable agent skill for turning press releases and supporting cases into media or creator collaboration briefs. It clarifies the audience, prioritizes communication objectives, proposes tailored content angles, and uses a separate HTML layout skill for presentation. Chinese is the default output language; other languages can be requested.

## 能做什么

- 先确认合作类型、媒体名称，或社交平台与博主信息，以及可用的案例素材。
- 从原稿标题中选择最有传播力的一条作为核心信息（KM）。
- 在产品增长、业务／品牌影响力与讨论度之间确定一个首要目标，再写次要目标。
- 面向博主提供评测、种草和体验角度；面向媒体提供消息选题及一到两段解读。
- 补齐合作方理解业务所需的事实、产品说明和行业分析背景。
- 将可用的视频、图片或演示链接放在相应角度或背景说明旁；不能嵌入时保留说明与链接。

输出通常包含传播背景、传播目的、内容角度、背景材料，并可按需增加合作支持。两类合作方同时需要材料时，分别生成独立可读的版本。

## 安装

将本仓库放入支持 `SKILL.md` 的工具所使用的技能目录。以 Codex 为例，默认目录是 `~/.codex/skills`；设置了 `CODEX_HOME` 时使用该目录下的 `skills`。

```sh
git clone https://github.com/alanyang0608-cmd/pr-content-collaboration-brief.git "${CODEX_HOME:-$HOME/.codex}/skills/pr-content-collaboration-brief"
```

目标目录已有同名技能时，先检查其来源并备份本地修改，避免覆盖自定义内容。

也可以从本仓库的 Releases 下载版本化 ZIP，解压后将完整的 `pr-content-collaboration-brief` 文件夹放入技能目录。目录结构如下：

```text
pr-content-collaboration-brief/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── README.md
└── LICENSE
```

## HTML 排版依赖

完整的 HTML 交付流程依赖单独安装的 `zep-html` 技能，本仓库不包含它。该名称是准确的技能调用标识。

如果该技能已在当前工具中可用，按其说明完成排版；也可以将它安装在同级技能目录，供本技能通过 `../zep-html/SKILL.md` 定位。没有此依赖时，本技能仍可整理内容草稿，并说明 HTML 排版尚未完成。

仓库本身无需 API 密钥。读取外部账号、案例链接或视频时，可能需要运行环境提供相应工具或访问权限。HTML 正文可离线阅读；远程媒体需要联网，随附本地视频需要保留附件目录。

## 使用

```text
请使用 $pr-content-collaboration-brief 整理下面这份新闻稿。
我需要媒体机构版和新媒体博主版。
媒体类型、社交平台与博主信息如下：……
可供使用的案例素材如下：……
新闻稿如下：……
```

合作对象或 Case 暂未确定也可以使用。技能会先确认缺失信息，并可按用户选择提供通用版。

## 事实与素材处理

- 区分正式可用内容、演示或试点案例与未来计划。
- 保留原始材料中的适用条件，不预设成功的评测结论。
- 行业分析与已核实事实分开；不编造统计数据、账号风格或视频内容。
- 技能文件仅保存通用方法，不附真实客户材料、内部业务资料、案例素材或私人路径。
- 实际 Brief 根据当次任务准确使用获准提供的业务事实；技能本身的泛化不意味着对所有 Brief 自动匿名化。

## License

[MIT](LICENSE). The license covers this repository's files. Separately installed skills and user-provided materials retain their own terms.
