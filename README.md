# It's 33 Lab · 轉職工具

轉職系列影片用到的線上工具。純靜態網頁，沒有後端、不蒐集任何資料。

## 目錄結構

```
/index.html                  首頁（文章與工具總覽）
/tools.html                  工具箱樞紐頁：找方向 → 看選項 → 做決定
/career-map.html             行銷職涯地圖（SVG 路線圖，資料在檔案裡的 NODES）
/assets/style.css            共用樣式，新頁面一律 link 這支，不要各自複製色票
/blog/*.html                 文章（EP1–EP5＋番外篇共 6 篇）
                             版型由 scratchpad 的 build_articles.py 統一生成，
                             改版型改那支就好，不要六個檔案各改一次
/ep5.html                    EP5 現有工作 vs 新工作 評量表（網址已寫在影片描述，不可搬動）
/vision.html                 反向願景產生器【人生篇專用】（規則式即時翻面，純前端、不呼叫 API）
/sitemap.xml, /robots.txt    給搜尋引擎用
```

**路徑一旦公開就不要再動。** 影片描述欄裡的連結是寫死的，
搬動資料夾會讓已經上片的影片連到 404。新集數的工具往下加新資料夾就好：

```
/ep6/index.html    ← EP6 的工具放這裡
```

## 怎麼部署到 GitHub Pages

### 第一次設定

1. 到 GitHub 建一個新的 repository，命名為 `你的帳號名稱.github.io`
   （例如帳號是 `shanyu33`，repo 就叫 `shanyu33.github.io`）。
   用這個名字，網址才會是乾淨的 `https://shanyu33.github.io/`，
   而不是多一層 `/repo名稱/`。
   建立時選 **Public**（GitHub Pages 免費方案需要公開的 repo）。

2. 把這個 `website` 資料夾裡的**所有內容**上傳到 repo 根目錄。
   最簡單的方式：repo 頁面 → Add file → Upload files → 把
   `index.html` 跟 `ep5` 資料夾一起拖進去 → Commit。

3. repo 頁面 → Settings → Pages →
   Source 選 **Deploy from a branch**，branch 選 **main**、資料夾選 **/ (root)** → Save。

4. 等一到兩分鐘，網址就會生效：
   - 首頁：`https://你的帳號.github.io/`
   - EP5 評量表：`https://你的帳號.github.io/ep5/`

### 之後要更新

改完檔案，重新上傳覆蓋就好，一分鐘左右生效。

## 要注意的事

- **repo 必須是 Public**，但這不代表有隱私問題——裡面只有網頁原始碼，
  沒有任何觀眾資料（因為根本沒有蒐集）。
- 網頁只依賴 Google Fonts 一個外部資源，其他全部內嵌，不會有連不到的問題。
- 觀眾填的答案存在他自己瀏覽器的 localStorage，不會送到任何地方，
  你我都看不到。公用電腦上填的內容會留在那台機器，這是瀏覽器的特性。
- 亮色／暗色主題都做了，跟觀眾的系統設定走。

## 上片前的檢查

- [ ] 用手機打開 `https://你的帳號.github.io/ep5/`，確認排版正常、可以點分數
- [ ] 把影片描述欄跟置頂留言裡的連結換成這個新網址
  （目前寫的是 claude.ai 的暫時連結，見 `ep5/YT標題描述.txt`）
