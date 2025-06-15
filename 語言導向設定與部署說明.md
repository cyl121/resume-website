
# 🌐 語言切換與導向邏輯說明（多語網站）

本網站支援「中英文雙語切換」，並透過 `home.html` 頁面自動導向對應語言版本。此文件整理語言偵測邏輯、頁面結構、部署技巧與注意事項，供後續維護與擴充使用。

---

## ✅ 語言導向核心邏輯

網站根目錄設有 `home.html` 為預設入口，使用 JavaScript 偵測瀏覽器語言：

```js
const lang = navigator.language || navigator.userLanguage;
if (lang.startsWith("zh")) {
  window.location.href = "index.html";      // 中文首頁
} else {
  window.location.href = "index-en.html";   // 英文首頁
}
```

### 🎯 行為說明：

| 瀏覽器語言     | 導向頁面        |
|----------------|-----------------|
| zh-TW / zh-CN  | index.html      |
| en-US / en-GB  | index-en.html   |

---

## 🗂 頁面結構與命名對應

| 中文頁面              | 對應英文頁面          |
|-----------------------|------------------------|
| `index.html`          | `index-en.html`        |
| `resume.html`         | `resume-en.html`       |
| `projects.html`       | `projects-en.html`     |
| `contact.html`        | `contact-en.html`      |

---

## 🧭 導覽列設定建議

每個語系頁面都應有**獨立的導覽列指向本語系**，避免跳轉錯亂：

```html
<!-- 英文頁導覽列 -->
<a href="index-en.html">Home</a>
<a href="resume-en.html">Resume</a>
<a href="projects-en.html">Projects</a>
<a href="contact-en.html">Contact</a>
```

```html
<!-- 中文頁導覽列 -->
<a href="index.html">首頁</a>
<a href="resume.html">履歷</a>
<a href="projects.html">作品集</a>
<a href="contact.html">聯絡我</a>
```

---

## 🧪 測試建議

- 使用 Chrome 無痕視窗測試 home.html
- 在 Console 輸入 `navigator.language` 確認語言是否為 `en-US` 或 `zh-TW`
- 測試英文與中文導覽連結是否互不干擾
- 若要手動切換語言，可直接輸入網址 `index-en.html` 或 `index.html`

---

## 🌐 Google 搜尋引擎語言支援（SEO）

每頁應加上 `<link rel="alternate" hreflang="...">`：

```html
<!-- 放在 head 裡 -->
<link rel="alternate" hreflang="zh-Hant" href="https://yourdomain/index.html" />
<link rel="alternate" hreflang="en" href="https://yourdomain/index-en.html" />
```

---

## ❗ 注意事項與維護建議

- ❌ 不建議加「語言切換按鈕」，會造成手機版排版亂掉
- ✅ 建議只用自動導向（home.html）＋網址路徑進行語言分流
- ✅ 所有英文頁面的連結都應指向 `-en.html` 結尾頁
- ✅ 每次新增語言頁面時，都需要維護對應導航與 hreflang

---

## 📁 部署建議（GitHub Pages）

1. 上傳 `home.html` 為入口頁面
2. 到 GitHub Pages 設定將首頁設為 `/home.html`
3. 確保所有頁面皆上傳正確並路徑一致

---

本文件可作為多語系靜態網站維護標準流程。
