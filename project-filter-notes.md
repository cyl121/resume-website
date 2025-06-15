
# 🔖 作品集篩選功能補充筆記（內部用）

## 🎯 功能目標
使用 `filterProjects(category)` 函式 + `class` 名稱對應分類，實現點按按鈕就能顯示特定類別的作品。

---

## 📌 class 與按鈕對應關係表

| 類別說明     | 對應的 class        | 按鈕寫法                                |
|--------------|----------------------|-----------------------------------------|
| 全部         | —（不需加 class）    | `<button onclick="filterProjects('all')">全部</button>` |
| 前端作品     | `frontend`           | `<button onclick="filterProjects('frontend')">前端作品</button>` |
| 全端/後端作品 | `backend` 或 `fullstack` | `<button onclick="filterProjects('backend')">全端作品</button>` |
| APP 專案     | `app`                | `<button onclick="filterProjects('app')">APP 開發</button>` |
| AI / LLM 專案 | `llm`                | `<button onclick="filterProjects('llm')">LLM 專案</button>` |
| 設計作品     | `design`（你可自定） | `<button onclick="filterProjects('design')">設計作品</button>` |

---

## 🧩 卡片結構範例（可多個分類同時出現）

```html
<div class="project-card frontend backend">
  <img src="./img/project5.png" alt="全端作品">
  <h3>支付系統</h3>
  <p>前後端整合、使用 Node.js 與 MySQL。</p>
  <a href="#">前往查看 →</a>
</div>
```

---

## 🧠 JavaScript 篩選邏輯

```js
function filterProjects(category) {
  const cards = document.querySelectorAll('.project-card');
  cards.forEach(card => {
    if (category === 'all') {
      card.style.display = 'block';
    } else {
      card.style.display = card.classList.contains(category) ? 'block' : 'none';
    }
  });
}
```

---

## ✨ 進階版 JS（淡出卡片，UX 更柔和）

```js
function filterProjects(category) {
  const cards = document.querySelectorAll('.project-card');
  cards.forEach(card => {
    if (category === 'all' || card.classList.contains(category)) {
      card.style.opacity = '1';
      card.style.pointerEvents = 'auto';
    } else {
      card.style.opacity = '0';
      card.style.pointerEvents = 'none';
    }
  });
}
```

---

## ✅ 實作重點提醒

- class 名稱需一致，**不能拼錯**
- 一張作品卡可以同時屬於多個分類
- 按鈕按下後 JS 就會控制顯示與隱藏
- 分類名稱可以自由命名：`ai`, `game`, `iot` 皆可
