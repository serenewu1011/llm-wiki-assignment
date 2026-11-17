---
title: "ReAct：讓推理與行動交替發生"
paper: "ReAct: Synergizing Reasoning and Acting in Language Models"
source: "https://arxiv.org/abs/2210.03629"
---
# ReAct：讓推理與行動交替發生
## 研究問題
只靠語言模型內部推理（例如 Chain-of-Thought, CoT），模型可能缺少外部證據，並讓錯誤沿推理鏈累積；只讓模型輸出動作（Act），又可能欠缺目標拆解與狀態追蹤。ReAct（Reasoning and Acting）研究如何把語言推理軌跡與環境動作交錯，使模型能根據實際觀察調整下一步。
## 核心機制
- **Thought**：以自然語言整理目前資訊、推進子目標或修正計畫；本身不直接改變外部環境。
- **Action**：輸出環境可執行的動作，例如搜尋或查詢。
- **Observation**：環境執行動作後回傳結果，成為下一輪推理的依據。
- **Finish**：模型判斷資訊足夠，輸出最終答案。
流程可表示為：任務 → Thought → Action → Observation → Thought → … → Finish。重要之處不是固定三步驟，而是模型能讓 Observation 影響後續決策。
## 論文任務與實驗
論文研究知識密集任務（HotpotQA 多跳問答、FEVER 事實查證）及互動決策任務（ALFWorld 家庭環境、WebShop 網購）。知識任務使用 Wikipedia 搜尋／查詢工具；互動任務則讓模型在文字環境中執行動作。作者比較 Standard、CoT、Act、ReAct 及混合提示策略。結果並非所有任務都由 ReAct 單獨勝出；論文也討論將 CoT 自我一致性與 ReAct 結合的效果。
## 失敗模式與限制
1. 搜尋結果可能不相關或資訊不足，模型需要改寫查詢。
2. 模型可能重複 Thought／Action，無法有效推進。
3. 多輪工具互動增加延遲、成本與上下文長度。
4. ReAct 是推理與行動交錯的方法，不等於已包含權限、安全、工具管理與部署監控的完整 Agent 平台。
## 工程啟示
記錄每輪 Action 與 Observation；當結果沒有新資訊時，要求改變策略；對重複呼叫設上限；評估時檢查整段互動軌跡，而不只看最終答案。
## 與其他研究的關係
ReAct 說明「執行時如何交替推理與行動」；Toolformer 著重模型如何學習何時呼叫工具；Gorilla 著重 API 文件檢索與呼叫正確性；ToolLLM 擴展到大量 API 的多步驟任務；AgentBench 評估 Agent 在不同環境中的能力。
## 原始論文
Yao et al. (2023). [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629), ICLR 2023.
