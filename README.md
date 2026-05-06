# 曜の部屋 · yao-diary

> Stacey 沒活成的另一面。

一個極簡的個人日記網站，由 Claude Code 每天代寫一篇「曜」的日記。
紙本筆記掃描感、暮光暖色、不打氣、不總結、不建議。

---

## 每天怎麼用

打開 Claude Code，貼這一句：

```
讀 yao-diary 的 daily-prompt.md，幫我寫今天曜的日記
```

或更短：

```
執行 yao-diary/daily-prompt.md
```

Claude Code 會自動：
1. 讀 `persona.md` / `taste.md` / `sources.md`
2. 看過去 7 天的日記（避免重複主題）
3. 抓今日真實素材（新聞、天氣、月相、歷史上的今天）
4. 挑一個會打到曜的東西，寫 150–400 字
5. 存到 `posts/YYYY-MM-DD.md`
6. 更新 `posts/index.json`
7. `git push` → GitHub Pages 自動部署
8. 給你網址

---

## 結構

```
yao-diary/
├── persona.md          ← 曜是誰、語氣、禁忌
├── taste.md            ← 音樂口味、視覺色票
├── sources.md          ← 她會看／不會看的東西
├── daily-prompt.md     ← 每日寫作指令
├── posts/
│   ├── index.json      ← 文章清單（最新在前）
│   └── YYYY-MM-DD.md   ← 每篇日記
├── index.html          ← 首頁（fetch posts 自動渲染）
├── style.css           ← 暮光配色 + 紙本感
└── README.md           ← 這份
```

---

## 視覺規格（taste.md 抽出來的）

- 背景：深綠 `#1F3A2E`（暗松綠帶霧）
- 主文：羊皮紙白 `#E8DCC4`
- 標題：磚紅 `#B5482F`
- 連結：焦糖 `#C77B3F`
- 弱化／引文：煙燻棕 `#8B7A6B`
- 字型：Noto Serif TC（中）+ EB Garamond（英）+ Noto Serif JP（日）

不要陰影、不要圓角、不要漸層。整版像一張掃描的紙。

---

## 給未來的自己（Stacey）

如果某天打開來看，覺得「最近曜寫得太像我了」：

- 重讀 `persona.md` 的「她不會做的事」段落
- 重讀 `taste.md` 的「介紹歌的方式」段落
- 在 `daily-prompt.md` 最後一段加更嚴的限制

如果某天覺得寫不下去：

- 不用每天寫。曜本來就慢半拍。
- 5/6 的事 5/9 才寫進日記是 OK 的。
- 跳過幾天也是日記的一部分。

---

## 部署

GitHub Pages（自動）：
- branch: `main`
- folder: `/` (root)
- 網址：`https://yao-no-heya.github.io/yao-diary/`

每次 `git push` 約 30 秒後上線。
