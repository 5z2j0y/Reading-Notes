将 LLM 与外部数据、工具、和复杂逻辑结合

#### langchain的好处
- 接入数据库，调用外部数据
- 与工具互动，如使用计算器、搜索引擎
- 任务链（Chains），把多个llm调用串联起来
- 记忆能力，在多轮对话中保持上下文

#### langchain的组件
- 模型
- 提示工程：支持动态填充
- 任务链：串联/动态选择
- 工具（Tools）：如python解释器、搜索引擎、sql
- Agents（代理）：能够自主决策并执行一系列操作的组件
- 记忆：短期/长期记忆（存入数据库）
- 数据连接（Retrievers & Vector Stores）：从外部数据源获取数据

