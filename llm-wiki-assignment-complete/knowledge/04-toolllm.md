---
title: "ToolLLM：大量真實 API 的多步驟任務"
paper: "ToolLLM: Facilitating Large Language Models to Master 16000+ Real-world APIs"
source: "https://arxiv.org/abs/2307.16789"
---
# ToolLLM：大量真實 API 的多步驟任務
## 研究問題
真實指令往往需要多個 API 串接，而不是呼叫單一工具。例如先搜尋資訊、取得細節，再依結果決定下一個工具。ToolLLM 探討如何讓模型面對大量真實 REST API，進行工具選擇與多輪呼叫。
## ToolBench 資料建置
論文描述從 RapidAPI Hub 收集 16,464 個 REST API，涵蓋 49 個類別；再利用 ChatGPT 生成多樣化指令及可能的 API 解題路徑。資料除了工具描述，也包含多步驟的呼叫軌跡。
## DFSDT：搜尋與回溯
Depth-First Search-based Decision Tree（DFSDT）以決策樹方式探索候選工具呼叫。當目前路徑無法完成任務時，可回溯並嘗試其他分支；相較只沿單一路徑生成，這能提供替代路徑探索。簡單情況可近似直線式工具使用，複雜情況則需要搜尋與回退。
## ToolLLaMA、Retriever 與 ToolEval
- **ToolLLaMA**：以 ToolBench 資料訓練，學習使用工具完成指令。
- **API Retriever**：從大量 API 中找出相關候選，縮小選擇範圍。
- **ToolEval**：評估工具使用路徑與任務完成情況。
## 研究貢獻與限制
ToolLLM 將工具使用研究推向大量真實 API、多步驟路徑與自動評估。仍需注意 API 文件可能過時、服務可能失效、不同路徑可能都能完成任務，而自動評估器也可能有偏差。實際部署還要處理權限、成本、錯誤回復與副作用。
## 與其他研究的關係
ReAct 提供交錯推理與行動的基本思路；Toolformer 著重模型如何學習呼叫工具；Gorilla 著重 API 文件檢索與呼叫生成；ToolLLM 著重大量 API 的多步驟任務；AgentBench 評估 Agent 在多種互動環境中的能力。
## 原始論文
Qin et al. (2023). [ToolLLM: Facilitating Large Language Models to Master 16000+ Real-world APIs](https://arxiv.org/abs/2307.16789), ICLR 2024.
