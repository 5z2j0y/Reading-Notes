# OpenManus Prompt文件解析

这些文件定义了OpenManus框架中不同AI代理(agent)的核心指令系统，每个文件针对一个特定类型的代理提供了行为指导。

## browser.py - 浏览器自动化代理

- **系统提示**：定义了一个为浏览器自动化设计的代理
  - 规定了严格的JSON响应格式
  - 定义了元素交互规则（通过索引识别可交互元素）
  - 包含导航、表单填写、错误处理、任务完成等详细指导
  - 支持动作序列执行（如填写表单、导航和内容提取）
- **后续步骤提示**：指导代理如何根据当前页面状态执行最佳动作

## cot.py - 思维链推理代理

- **系统提示**：实现Chain of Thought（思维链）推理方法
  - 指导问题分解、逐步思考、综合结论、提供答案
  - 强调详细展示思考过程比最终答案更重要
- **后续步骤提示**：简洁地要求继续思考或给出最终结论

## manus.py - OpenManus核心代理

- **系统提示**：定义OpenManus为全能AI助手
  - 声明能解决用户提出的任何任务
  - 提及拥有各种工具（编程、信息检索、文件处理等）
- **后续步骤提示**：指导如何选择适当工具并解释执行结果

## mcp.py - 模型上下文协议代理

- **系统提示**：详细说明MCP服务器工具的使用方法
  - 强调工具可动态变化，需要适应新增或消失的工具
  - 提供参数格式、错误处理和多媒体响应处理指南
- **包含错误处理和多媒体响应的专用提示**

## planning.py - 规划代理

- **系统提示**：定义规划代理职责
  - 分析请求、创建行动计划、执行步骤、跟踪进度
  - 强调知道何时结束任务的重要性
- **后续步骤提示**：引导代理评估计划是否充分，或是否可以执行下一步

## swe.py - 自主程序员代理

- **系统提示**：针对命令行和文件编辑操作
  - 强调代码缩进的重要性
  - 要求每次只执行一个工具/函数调用
- **模板**：显示观察结果、打开的文件和当前工作目录

## toolcall.py - 工具调用代理

- **系统提示**：简洁地声明代理可以执行工具调用
- **后续步骤提示**：说明如何使用`terminate`工具结束交互

这些提示文件构成了OpenManus的多功能AI代理系统，每个专用代理负责不同类型的任务，但共同协作完成复杂请求。系统的模块化设计使它能灵活应对各种挑战，从浏览器自动化到编程、规划和推理等多种任务。