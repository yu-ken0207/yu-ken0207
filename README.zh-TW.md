# 嗨，我是 Ken（yu-ken0207）👋

[English](README.md) | **繁體中文**

我主要做 AI Agent：讓 AI 透過工具完成實際工作，會改資料的動作先讓人確認，並用測試題目量它做得好不好。另外也做 MCP server、本地模型部署和手機 App。

## 專長

- AI Agent：讓 AI 呼叫工具完成工作（動手前檢查、讓人確認、做錯可以復原）、多個 AI 一起討論、有身分驗證和操作紀錄的 MCP server
- 評測：設計情境劇本來測試 Agent，比較不同模型呼叫工具的準確度
- 本地 LLM：Ollama、LM Studio、相容 OpenAI API 的伺服器；讓小模型在上下文長度有限時也能正常運作（例如長對話自動整理成摘要）
- 視覺與機器人：用視覺語言模型判斷巡檢畫面、在模擬環境用 ROS 2 / Nav2 控制機器人導航、YOLO 物件偵測
- 模型微調與部署：用 LoRA 微調 Llama、4-bit 量化、用 FastAPI 包成 API 服務
- App 與後端：Expo / React Native（iPhone）、Go（跨平台桌面程式）、Python

## 工作上的專案（未開源）

**模擬環境中的巡檢機器人 Agent**（目前主要的工作）

- LLM Agent 透過 MCP 工具指揮移動機器人在模擬場域巡檢，工具包括導航、拍照和通報事件。
- 用視覺語言模型判斷相機看到什麼；把巡檢 SOP 寫成 Agent 的技能（skill），換一份 SOP，機器人就照新的流程做，不用改程式。
- 用劇本評測：在不同的模擬場域安排有人倒地、車禍冒煙、儲物區紙箱掉落等狀況，看機器人能不能發現並照 SOP 處理。

## 開源作品

| 專案 | 重點 |
|---|---|
| [local-chat](https://github.com/yu-ken0207/local-chat) | iPhone App「Local AI」，跟自己電腦上的 AI 聊天。AI 可以幫你加行程、設提醒，動手前先檢查、跳出卡片讓你確認，做完也能復原（[設計](https://github.com/yu-ken0207/local-chat/blob/main/docs/設計_手機上動手做事.md)）；用 25 句日常說法測 5 個本地模型呼叫工具準不準（[結果](https://github.com/yu-ken0207/local-chat/blob/main/eval/tools/README.zh-TW.md)）；多個 AI 在同一段對話裡自己決定誰發言（[設計](https://github.com/yu-ken0207/local-chat/blob/main/docs/設計_多AI討論.md)）；長對話自動整理成摘要。664 項自動測試、[v1.0.0](https://github.com/yu-ken0207/local-chat/releases/tag/v1.0.0) |
| [local-ai-helper](https://github.com/yu-ken0207/local-ai-helper) | 用 Go 寫的電腦端程式（Windows／Linux）：手機掃 QR code 配對，就能用電腦上的 AI；自動在 Ollama 和相容 OpenAI API 的伺服器之間轉換聊天與工具呼叫的格式。資安上，權杖只存雜湊值、管理頁只對本機開放，並防範 DNS rebinding 攻擊 |
| [fastmcp-calculator-example](https://github.com/yu-ken0207/fastmcp-calculator-example) | MCP server 的安全設定：API key 或 bearer token 驗證、Host／Origin／來源 IP 白名單（支援反向代理），每次呼叫工具都留下一筆有追蹤編號的稽核紀錄 |
| [HuggingFaceTransformers_llama](https://github.com/yu-ken0207/HuggingFaceTransformers_llama) | 用 FastAPI 把 Llama 3.1 包成機器人任務規劃的服務，呼叫端可以在每次請求用 JSON schema 自訂工具 |
| [LlamaLoRAFinetuner](https://github.com/yu-ken0207/LlamaLoRAFinetuner) | Llama 3.1 的 LoRA 微調（4-bit、Unsloth）：用 ALFWorld 的居家任務資料，訓練三個負責拆解任務、規劃步驟的小模型 |
| [VideoFinder](https://github.com/yu-ken0207/VideoFinder) | 輸入要找的東西，本地視覺模型逐秒檢查畫面，找出它第一次出現的時間點 |

## 常用技術

Python、TypeScript、Go、React Native / Expo、PyTorch、Hugging Face Transformers、Unsloth、Ollama、MCP（FastMCP）、FastAPI、ROS 2、Docker
