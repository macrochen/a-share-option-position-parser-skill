# a-share-option-position-parser-skill

一个基于 AI 视觉大模型（Multimodal Vision）的 A 股期权持仓明细解析工具。

## 功能特性
- **直接截图解析**：支持直接上传 A 股期权持仓界面的截图，无需额外输入。
- **自动读取目录**：如果未上传截图，自动读取 `~/Downloads/options/` 目录下的最新文件。
- **智能数据提取**：准确提取标的、到期日、期权类型、行权价、开仓价、现价、盈亏金额和持仓数量。
- **卖方自动识别**：能智能识别界面中的“保”字标识（保证金交易），自动将卖出开仓的持仓数量转为负数。
- **内置交叉验算**：内部结合 A 股期权 10000 乘数，自动校验提取价格与盈亏的逻辑自洽性。
- **结构化 JSON 输出**：每次生成全新数据，结果强制覆盖并结构化输出至本地的 JSON 文件中。

## 用法
1. 确保该 Skill 目录位于个人 agents skills 库中。
2. 在对话中上传一张 A 股期权持仓界面的截图，或者提前将截图放入 `~/Downloads/options/` 目录。
3. 告诉 Agent：“解析期权持仓”。
4. 解析后的结果会自动保存在 `~/outputs/a-share-option-position-parser-skill/<YYYY-MM-DD-描述>/position_data.json` 文件中。
