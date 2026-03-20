# 🎨 Performi Layout
Performi 後台管理系統共用版型（Layout）元件

---

## 📌 專案簡介

本元件為 Performi 系統的共用版型（Layout）核心，負責整體後台介面的結構與使用者操作體驗，包含：

- 側邊選單（Sidebar）
- 權限導向的動態選單顯示
- 多語系切換
- 使用者資訊載入與登出
- 響應式版面支援（Desktop / Mobile）
- 管理者 / 主管 / 一般使用者分層導覽

此 Layout 作為整個系統的入口框架，讓各功能頁面能在一致的 UI/UX 結構下運作，同時確保不同角色僅能看到對應權限頁面。

---

## 🎯 設計目的

在企業內部系統中，後台版型不只是畫面容器，而是整合下列能力的核心介面層：

- **統一導航體驗**：所有頁面使用一致的側邊欄與頁面框架
- **角色權限管理（RBAC + Page-level Control）**
- **多語系支援（i18n）**
- **響應式設計（Responsive UI）**
- **模組化擴充（Scalable Architecture）**

---

## 🧩 核心功能

### 1. 使用者登入狀態與資料載入
系統啟動時會自動讀取目前登入者資訊：

- 使用者姓名 / Email
- 部門 / 職位
- 職位層級
- 系統角色（admin / user）

未完成資料設定者將導向 Role Setup 頁面。

---

### 2. 動態權限導向選單

#### 一般區塊（General）
- Dashboard
- Data Entry
- 批量 KPI 設定（依權限）
- 生產效能分析（依權限）
- 寶典資料庫
- 使用者指南

#### 團隊區塊（Team）
（管理職可見）
- Review Center
- KPI Management
- Team Management
- Turnover Analysis

#### 管理區塊（Admin）
（僅 admin）
- Notification Management
- Access Management
- Organization Settings

---

### 3. 多語系支援（i18n）
- 中文 / 英文切換
- UI 自動適配文字長度
- Sidebar 排版動態調整

---

### 4. 響應式設計（Responsive）

#### Desktop
- 完整 Sidebar
- 分組選單

#### Mobile
- Top bar + SidebarTrigger
- 可收合導覽

---

### 5. 使用者系統
- 顯示姓名 / 職稱 / 身份
- Admin 標記
- 安全登出機制

---

## 🏗 系統架構概念

```text
User Login
   ↓
User.me()
   ↓
Role / Position / Profile
   ↓
PageAccessConfig
   ↓
Navigation Generation
   ↓
Sidebar Rendering
   ↓
Main Content
