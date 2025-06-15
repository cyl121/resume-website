# 個人履歷網站

這是我使用 HTML、CSS、JavaScript 所製作的個人履歷網站，內容包含：

- 🌟 自我介紹
- 📄 履歷資訊（學歷、技能條列）
- 🧰 技能展示（附圖示）
- 📂 專案作品集（含連結）
- 📬 聯絡表單（EmailJS）
- 🌙 深色模式切換
- 📱 響應式設計（支援手機瀏覽）

👉 **網站連結**：  
🔗 [https://cyl121.github.io/resume-website/](https://cyl121.github.io/resume-website/)

---

## 🔧 技術堆疊

- HTML5 / CSS3 / JavaScript
- EmailJS 表單寄送
- GitHub Pages 部署

---

## 🚀 使用方式

1. 本專案為純前端，無需後端伺服器。
2. 可直接 clone 後開啟 `index.html` 頁面。
3. Email 表單功能需至 EmailJS 申請免費帳號並替換對應 ID。

---

## 📜 授權

本專案僅作為個人履歷作品展示用途，歡迎參考但請勿直接抄襲。

---

## 📌 補充說明：作品分類與篩選邏輯

此網站的作品集頁面支援分類功能，使用 JS 與 class 名稱比對進行篩選。篩選邏輯如下：

### 篩選按鈕用法：

```html
<button onclick="filterProjects('frontend')">前端作品</button>
<button onclick="filterProjects('backend')">全端作品</button>
<button onclick="filterProjects('llm')">LLM 專案</button>
```

### 對應卡片結構：

```html
<div class="project-card frontend backend">
  <h3>支付系統</h3>
  <p>整合 Node.js + MySQL 與前端介面</p>
</div>
```

> 每張卡片可同時屬於多個分類，透過 class 指定類別名稱。

---

如需詳細筆記，請參考附加檔案：  
📄 [`project-filter-notes.md`](./project-filter-notes.md)

