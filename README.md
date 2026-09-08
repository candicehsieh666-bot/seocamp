# SEO/社群實戰共學營 — 作業繳交區

營期 2026/9/7 – 11/2，共 8 週。學員在這裡繳交每週作品、互相回饋，並追蹤保證金狀態。

## 檔案

- `index.html` — 整個系統就這一個檔案，不需要編譯或安裝
- `firestore-rules.txt` — Firebase 資料庫的安全規則，要貼到 Firebase Console

## 要改東西的話

打開 `index.html`，最上面有兩區可以改：

| 位置 | 可以改什麼 |
|---|---|
| 第 16 行 `THEME_NAME` | 配色：`'blue'` / `'brown'` / `'purple'` |
| — | 學員名單**不在這個檔案裡**，見下面「改名單」 |
| 設定區 `CAMP_WEEKS` | 每週的截止日與回饋期限 |
| 設定區 `DEPOSIT_TOTAL` 等 | 保證金金額與扣款規則 |

改完存檔，GitHub Pages 會在 1–2 分鐘後自動更新。

### 改名單

學員名單存在 Firebase，不在程式碼裡，所以公開的 repo 看不到學員名字。
要加人或改名：Firebase Console → Firestore → 這個路徑的 `names` 欄位

```
artifacts / seo-camp-portal-v1 / public / data / config / roster
```

改完學員重新整理頁面就生效，不用重新上傳檔案。

**注意**：作業和回饋都是用「名字」對應到人的。把既有的名字改掉，那個人先前的紀錄會對不起來，需要連 Firestore 裡的舊資料一起換。

## 資料存在哪

Firebase Firestore，專案 `test-fee8d`，資料區 `seo-camp-portal-v1`。
換網址、換主機都不影響資料——網站只是外殼。

## 權限

學員用匿名身分登入，只能刪掉「自己在同一台裝置上送出的」內容。
跨裝置刪除、或要刪別人的東西，要從 Firebase Console 操作。
