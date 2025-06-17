
# 🧾 多語履歷網站發佈紀錄

本檔案記錄 Yu Lang Chou 的個人履歷網站建置與發佈歷程，包含語系導向、網頁架構、除錯記錄與最終部署完成確認。

---

## 📌 基本資訊

- 網站名稱：Yu Lang Chou Resume Website
- 專案類型：個人作品集 / 履歷網站
- 網站連結：[https://cyl121.github.io/resume-website/](https://cyl121.github.io/resume-website/)
- 開發技術：HTML、CSS、JavaScript、GitHub Pages
- 語言版本：繁體中文 / 英文
- 發佈平台：GitHub Pages

---

## 🗂 網站架構

```
resume-website/
├── zh/                     # 中文頁面
│   ├── index.html
│   ├── resume.html
│   ├── projects.html
│   └── contact.html
├── en/                     # 英文頁面
│   ├── index.html
│   ├── resume.html
│   ├── projects.html
│   └── contact.html
├── home.html               # 語言導向首頁
├── index.html              # 自動轉跳到 home.html
├── img/                    # 圖片資源
├── style.css               # 共用樣式表
├── README.md               # GitHub 說明文件
├── language-guide.md       # 語言導向與部署說明
```

---

## 🌐 語言導向實作

- 使用 `navigator.language` 判斷語言，自動從 `home.html` 導向 `zh/index.html` 或 `en/index.html`
- 網站不使用語言切換按鈕，避免手機排版錯亂
- 每語系獨立導覽列與結構，互不干擾

---

## 🔧 問題與修正紀錄

| 問題                         | 解法                                                   |
|------------------------------|--------------------------------------------------------|
| logo 圖片過大，佔滿畫面      | 補上 `.logo-img { max-width: 100px; width: auto; }`     |
| CSS 無法套用                 | 子資料夾頁面使用相對路徑 `<link href="../style.css">`   |
| 英文頁導覽列出現 404         | 原寫 `resume-en.html`，已改為 `resume.html` 並修正連結 |
| GitHub Pages 首頁跑出 README | 補上 redirect 的 `index.html` 導向 `home.html`         |
| home.html 永遠跳中文頁      | 測試方式：改語言環境、無痕模式、Console 檢查語系       |

---

## ✅ 發佈完成時間與狀態

- 發佈完成日：2025 年 6 月
- 最終確認項目：頁面結構、語言跳轉、CSS 套用、圖片載入、導覽連結
- 測試通過平台：桌機 Chrome / Safari / 手機模式
- 狀態：✅ 已完成並正式上線

---

## ✨ 備註

此專案為 Yu Lang Chou 的前端實作與網站整合成果，展示個人技能與完整部署能力，已可作為履歷、面試、作品集參考使用。
