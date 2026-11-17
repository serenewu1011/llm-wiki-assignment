# Ingest 與品質檢查紀錄
## 五篇資料整理狀態
| 論文 | 研究問題 | 核心方法 | 限制／邊界 | Wiki 初稿 |
|---|---|---|---|---|
| ReAct | 推理與行動如何交錯 | Thought–Action–Observation | 多輪成本、重複行動 | 已建立 |
| Toolformer | 模型如何學習工具呼叫 | 候選生成、執行、loss 篩選、微調 | loss 是代理指標 | 已建立 |
| Gorilla | 如何從大量 API 文件選對介面 | APIBench、Retriever、AST 評估 | API 呼叫正確不等於安全完成任務 | 已建立 |
| ToolLLM | 如何處理大量 API 多步任務 | ToolBench、DFSDT、ToolLLaMA、ToolEval | API 可用性與評估器偏差 | 已建立 |
| AgentBench | 如何評估 Agent 互動能力 | 八種互動環境 | benchmark 不等於真實世界全面可靠 | 已建立 |

## 檢查紀錄
- [x] 五篇論文皆有原始來源連結。
- [x] 五篇文章均包含研究問題、方法、限制及與其他研究的關係。
- [x] Loop / Graph 包含檢查與回退節點。
- [x] 反思明確指出容易混淆的研究定位。
- [ ] 需依老師指定的 LLM Wiki 平台補上實際 PDF ingest 證據（若要求）。
- [ ] 需逐表核對欲放入簡報的精確實驗數字；本版避免未核實數字。
