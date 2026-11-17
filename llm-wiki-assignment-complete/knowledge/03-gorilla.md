---
title: "Gorilla：從大量 API 文件選對工具與參數"
paper: "Gorilla: Large Language Model Connected with Massive APIs"
source: "https://arxiv.org/abs/2305.15334"
---
# Gorilla：從大量 API 文件選對工具與參數
## 研究問題
當工具數量增加、API 功能相似且文件持續更新時，模型可能選錯函式庫、幻覺不存在的函式，或產生不符合規格的參數。Gorilla 研究如何結合 API 使用資料訓練與文件檢索，提升 API 呼叫的正確性。
## 系統組成
- **APIBench**：整理 API 文件與對應指令，建立 API 使用資料。
- **指令資料生成**：為 API 文件產生自然語言需求，使模型學習需求與 API 之間的對應。
- **Gorilla 模型**：以語言模型微調，生成具體 API 呼叫。
- **Retriever**：推論時找出相關文件，提供當下 API 說明與參數規格。
- **AST 評估**：以抽象語法樹結構檢查生成呼叫，而不只比較文字表面是否相似。
## 為什麼檢索重要？
模型參數中的知識可能過時；API 名稱、參數及版本都可能改變。檢索器把相關文件帶進當前上下文，讓模型依據最新可用文件生成呼叫。這是「模型學會 API 模式」與「推論時取得當下規格」的結合。
## 評估與解讀
論文提出 APIBench，涵蓋 HuggingFace、TorchHub、TensorHub 等 API 生態，並評估模型能否生成正確 API 呼叫。論文的 AST 比對用來檢查呼叫結構與目標 API 的吻合程度。這類評估不代表模型已能安全執行所有 API，也不等於完成多步驟任務規劃。
## 限制
1. 文件品質、檢索召回率與版本資訊會影響輸出。
2. AST 結構正確不保證執行結果符合使用者真正意圖。
3. 權限、API 副作用、服務可用性與執行後驗證仍需系統層處理。
## 與其他研究的關係
Toolformer 問「何時呼叫工具」；Gorilla 更聚焦「大量 API 中選哪個，以及如何依文件產生呼叫」；ToolLLM 則把問題擴展到大量真實 REST API 與多步驟任務。
## 原始論文
Patil et al. (2023). [Gorilla: Large Language Model Connected with Massive APIs](https://arxiv.org/abs/2305.15334).
