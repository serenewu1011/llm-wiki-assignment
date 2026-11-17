---
title: "AgentBench：如何評估 LLM 是否能當 Agent？"
paper: "AgentBench: Evaluating LLMs as Agents"
source: "https://arxiv.org/abs/2308.03688"
---
# AgentBench：如何評估 LLM 是否能當 Agent？
## 為什麼需要 Agent Benchmark？
一般問答測試主要檢查模型輸出的文字；Agent 則必須在環境中觀察狀態、選擇動作、執行並持續修正。單輪問答分數無法充分反映模型能否操作資料庫、終端機、網頁或遵循多輪互動規則。
## 八種互動環境
AgentBench 提出八個環境，涵蓋 Operating System、Database、Knowledge Graph、Digital Card Game、Lateral Thinking Puzzles、House-Holding、Web Shopping 與 Web Browsing。這些環境有不同工具介面、狀態轉移及成功條件，可觀察模型能力是否只侷限於單一任務類型。
## 評估觀點
論文以多輪互動方式測試多種 API-based 與開源模型，觀察其在不同環境中的任務表現。作者指出，當時模型在長期推理、決策與指令遵循方面仍有挑戰。不同環境的分數代表不同任務能力，不宜簡化成單一「Agent 智商」。
## 為什麼多環境重要？
模型可能擅長網頁文字理解，卻不擅長 SQL；可能能產生 shell 指令，卻無法在多輪互動中追蹤狀態。多環境測試可暴露能力落差，也避免只憑單一 benchmark 宣稱 Agent 全面可靠。
## 限制
- 分數受環境、提示、模型版本與測試集影響。
- 不同環境指標未必可直接互相比較。
- 任務成功率無法完整代表安全性、成本、延遲與可恢復性。
- AgentBench 是評估基準，不是提升工具使用能力的訓練方法。
## 五篇研究的整體脈絡
ReAct：如何交替推理與行動？Toolformer：如何學會何時呼叫工具？Gorilla：如何選對 API 與參數？ToolLLM：如何完成大量 API 的多步任務？AgentBench：如何跨環境評估 Agent？
## 原始論文
Liu et al. (2024). [AgentBench: Evaluating LLMs as Agents](https://arxiv.org/abs/2308.03688), ICLR 2024.
