# A2X Registry Demo Data

A2X Registry 的演示与评估数据集集合。

## 数据集列表

| 数据集 | 服务数 | 查询数 | 语言 | 说明 |
|--------|:-----:|:-----:|:---:|------|
| [`ToolRet_clean`](./ToolRet_clean) | 1839 | 1714 | EN | 基于 [tool-retrieval-benchmark](https://github.com/mangopy/tool-retrieval-benchmark)，对低质量数据清洗后得到 |
| [`ToolRet_clean_CN`](./ToolRet_clean_CN) | 1839 | 1714 | ZH | `ToolRet_clean` 的中文翻译版 |
| [`publicMCP`](./publicMCP) | 1387 | 50 | EN | 源自 [MCP 官方服务器列表](https://github.com/modelcontextprotocol/servers) |
| [`publicMCP_CN`](./publicMCP_CN) | 1387 | 50 | ZH | `publicMCP` 的中文翻译版 |
| [`publicSkill`](./publicSkill) | 17 | — | EN | Claude Code Skill 集合 |
| [`default`](./default) | ~21 | — | EN | 公开 A2A Agent，启动时自动拉取 |

## 数据集结构

每个数据集目录包含以下标准文件：

```
<dataset>/
├── service.json              # 服务条目（name + description + 元数据）
├── user_config.json          # 用户/所有权配置
├── vector_config.json        # 向量检索配置
├── query/
│   ├── query.json            # 评估查询集（含 ground truth）
│   └── default_queries.json  # 默认演示查询
└── taxonomy/                 # A2X 自动构建的能力树
    ├── taxonomy.json
    ├── class.json
    └── build_config.json
```


## 数据来源声明

- **ToolRet_clean / ToolRet_clean_CN**：基于 [mangopy/tool-retrieval-benchmark](https://github.com/mangopy/tool-retrieval-benchmark)，原数据按 MIT 许可发布。本仓库在原数据基础上做了去重、字段规范化与低质量描述清洗。
- **publicMCP / publicMCP_CN**：基于 [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) 官方服务器列表，每条服务的 `name` / `description` / `homepage` 字段均来自该仓库。

如需引用本数据集，请同时引用上述上游来源。
