Medical Report NLP Parser (Lite Version)

這是一個基於 Python 的醫療文本處理工具庫，源自於實際參與的國家級癌症登記 AI 輔助計畫。
為了展示核心技術能力並遵守資料隱私規範，此 Repository 為去敏化 (De-identified) 與 重構 (Refactored) 後的精簡版本。

This is a desensitized and refactored version of a Biomedical NLP pipeline used for Cancer Registry. It demonstrates extracting structured data (TNM Staging) from unstructured pathology reports.

🚀 Key Features (核心功能)

Robust Text Normalization: 處理醫療報告中常見的全形字符、特殊符號與排版雜訊 (text_utils.py)。

Hybrid Date Parsing: 自動辨識並轉換「民國/西元」混合的日期格式，統一輸出為 ISO 格式。

Rule-based TNM Extraction:

運用 Advanced Regex 從非結構化文本中精準提取 AJCC 癌症分期 (pT/pN/pM)。

實作邏輯判斷優先級：優先解析 Summary 段落，若缺失則掃描全文 Context。

Logic Validation: 實作基礎的醫學邏輯檢核（例如：原位癌不應有遠端轉移）。

🛠️ Tech Stack

Python 3.9+

Regular Expressions (re): 用於複雜文本模式匹配。

Unicodedata: 用於字元正規化 (NFKC)。

📂 Project Structure

main.py: 程式進入點，模擬處理一筆病理報告的完整流程。

tnm_parser.py: 封裝了 TNM 分期的擷取邏輯與 Regex Patterns。

text_utils.py: 通用的字串清洗與日期處理 Helper functions。

💡 What I Learned (專案亮點)

在原始的大型專案中（未在此展示），我還負責：

整合 Llama 2 (LLM) 進行 RAG (Retrieval-Augmented Generation) 以處理更複雜的語意理解。

設計 Human-in-the-loop 流程，協助醫師驗證 AI 標註結果。

處理來自 130+ 家醫院、異質性極高的醫療數據格式。

(Note: The original InformapJ ontology service and hospital-specific logic have been removed for confidentiality.)
