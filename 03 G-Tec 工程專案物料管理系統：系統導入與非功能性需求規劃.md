# 03 G-Tec 工程專案物料管理系統：系統導入與非功能性需求規劃

* **文件版本**: 1.0
* **制定日期**: 2025年7月5日
* **制定者**: William He

---

**文件目的**：本文件旨在補充說明系統開發過程中，與功能需求同等重要的非功能性需求及導入策略，以確保系統能成功落地並被使用者接納。

---

### 1. 系統環境規劃 (Environment Planning)
為保障開發品質與系統上線後的穩定性，必須規劃並建置各自獨立的系統環境。

- **1.1 開發環境 (Development Environment)**: 供開發團隊日常開發與單元測試。
- **1.2 測試/UAT 環境 (Staging/UAT Environment)**: 供 QA 團隊進行完整測試，以及供使用者進行驗收測試 (UAT)。此環境應盡可能模擬正式環境。
- **1.3 正式環境 (Production Environment)**: 系統實際上線，供所有終端使用者日常作業的環境，具備最高的穩定性、安全性及完整的備份與災難恢復機制。

---

### 2. 資料轉移細化策略 (Detailed Data Migration Strategy)
資料轉移是系統上線前至關重要的一步，需及早與管理層及使用者溝通並確認範疇。

#### 2.1 轉移範圍界定
- **物料主檔**：建議初期僅轉移「目前仍在使用中」的物料，降低資料清洗的複雜度。
- **專案主檔**：必須轉移所有「進行中」的專案；建議轉移近 1-2 年「已結案」的專案，以利歷史資料分析。
- **庫存資料**：不轉移歷史異動記錄。在系統上線前，進行一次全面的實體庫存盤點，將盤點結果作為「期初庫存開帳」資料，一次性匯入新系統。

#### 2.2 轉移流程
1.  **資料提取 (Extract)**: 從舊系統或 Excel 文件提取資料。
2.  **資料清洗與轉換 (Transform)**: 根據新系統格式進行清理、轉換，此階段需使用者深度參與。
3.  **資料載入 (Load)**: 將整理好的資料載入 UAT 環境進行測試。
4.  **資料驗證**: 由使用者在 UAT 環境中驗證資料的正確性與完整性。
5.  **正式導入**: 在正式上線前，重複以上流程，將最終確認的資料導入正式環境。

---

### 3. 變革管理策略 (Change Management Strategy)
系統的成功不僅在於技術，更在於「人」的接納。

#### 3.1 溝通計畫 (Communication Plan)
- 持續性地向所有利害關係人說明系統導入的目標、好處與時程規劃。

#### 3.2 種子使用者計畫 (Seed/Power User Program)
- **目的**：在各部門挑選對新科技接受度高、具影響力的員工成為「種子使用者」。
- **職責**：前期參與測試提供回饋、中期協助推廣、後期成為部門內的「第一線小老師」，協助解答基本操作問題。

#### 3.3 使用者培訓計畫 (User Training Plan)
- **分眾培訓**：根據不同角色設計不同課程，避免資訊過載。
- **動手實作**：培訓應在 UAT 環境中進行，讓學員實際操作。
- **提供教材**：製作簡單易懂的操作手冊或教學短片，方便隨時查閱。

#### 3.4 上線後支援計畫 (Post Go-Live Support Plan)
- **目的**：確保系統上線初期使用者遇到的問題能被有效率地解決。
- **內容**：
    - **問題回報管道**：建立明確、統一的回報方式 (如：IT服務台、專用郵箱)。
    - **服務等級協議 (SLA)**：定義問題的優先級與預計解決時間。
    - **常見問題手冊 (FAQ)**：彙整上線後常見問題及其解決方案，供使用者自助查詢。