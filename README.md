# CaveDuck 前端白名單查詢系統
# CaveDuck Frontend Whitelist Reference

針對 CaveDuck 平台的 HTML/CSS 白名單查詢工具，整合聊天室與角色介面的**實測資料**，支援即時搜尋、分類篩選與視覺預覽。

A hands-on whitelist reference tool for the CaveDuck platform. All support statuses are based on real tests conducted in both the chat room and the character creator, not theoretical specs.

🔗 `https://saltenfish.github.io/black-white_list_0529/`

---

## 頁面說明 / Pages

### 🏷️ HTML 標籤 `html-tags.html`

137 個 HTML 標籤的完整實測對照表，包含：

- 聊天室與角色介面各自的支援狀態（✓ / ✗）
- DOMPurify 白名單、xss 套件白名單
- 各標籤允許使用的屬性清單
- 每個有效標籤的**視覺預覽**與**可複製程式碼**

A complete reference for all 137 HTML tags, showing:

- Per-interface support status (chat room vs. character page)
- DOMPurify and xss package whitelist membership
- Allowed attributes per tag
- A **live visual preview** and **copyable code snippet** for every tag that works in at least one interface

> 💡 卡片左側色條代表支援範圍：綠 = 兩者皆可 / 黃 = 僅聊天室 / 藍 = 僅角色介面 / 紅 = 不支援
>
> 💡 The left border color indicates support scope: green = both / yellow = chat only / blue = character page only / red = unsupported

---

### 🎨 CSS 屬性 `css-props.html`

Inline `style=""` 可使用的 CSS 屬性清單，分三個層級：

| 層級 | 說明 |
|---|---|
| 🟢 兩者皆可 | 聊天室與角色介面均支援 |
| 🟡 僅聊天室 | 聊天室支援（DOMPurify 不過濾 inline style） |
| 🔴 不支援 | FilterCSS 攔截，兩種介面均不可用 |

A categorized list of CSS properties usable in inline `style=""` attributes, split into three tiers:

| Tier | Description |
|---|---|
| 🟢 Both | Supported in both chat room and character page |
| 🟡 Chat only | Allowed in the chat room (DOMPurify does not filter inline styles) |
| 🔴 Unsupported | Blocked by FilterCSS in both interfaces |

> 💡 聊天室的 inline style 幾乎不受限制；角色介面僅支援 FilterCSS 白名單內的屬性。
>
> 💡 The chat room permits nearly all inline styles. The character page is restricted to properties on the FilterCSS allowlist.

---

### 🔷 SVG 標籤 `svg.html`

SVG Core 標籤與 Filter 濾鏡元素清單，含 SVG 視覺預覽。**僅聊天室支援。**

SVG core tags and filter elements with live SVG previews. **Chat room only** — the character page strips all SVG content.

---

### ∑ MathML `mathml.html`

MathML 數學標記標籤清單，含即時公式渲染預覽。**僅聊天室支援。**

MathML tags with live formula rendering previews. **Chat room only** — the character page does not render MathML.

---

### ✨ Animate.css `animate.html`

111 個 Animate.css 動畫類別，提供持續播放的動畫預覽，以及完整的 `<span class="animate__animated animate__xxx">` 複製程式碼。

111 Animate.css classes with looping live previews and full copyable `<span class="animate__animated animate__xxx">` code.

---

### 💠 Tailwind `tailwind.html`

920 個 Tailwind CSS class 的白話說明與支援狀態，分頁顯示。

920 Tailwind CSS classes with plain-language descriptions and support status, paginated for performance.

---

### 🔗 CaveDuck Class Reference（外部連結 / External Link）

由 [@prysline]製作的 CaveDuck 平台 class 查詢工具，收錄平台自定義 class 的完整說明。

A CaveDuck class reference tool created by [@prysline], covering the platform's custom class definitions in detail.

🔗 `https://prysline.github.io/caveduck-class-reference/`

---

### 🎠 Swiper.js `swiper.html` *(次要參考 / Secondary)*

Swiper.js 輪播元件的 class 對照表，含完整樣式值。

Swiper.js carousel component class reference with full style values.

### 📐 CSS 變數 `css-vars.html` *(次要參考 / Secondary)*

414 個 CaveDuck 平台內建的 CSS 自訂變數及其預設值。

414 built-in CSS custom variables from the CaveDuck platform with their default values.

---

## 使用方式 / How to Use

1. 開啟首頁 `index.html`，點擊任一卡片進入對應工具頁。
2. 使用頂部**搜尋欄**輸入關鍵字，即時篩選結果。
3. 使用**篩選按鈕**依支援範圍過濾（全部 / 兩者皆可 / 僅聊天室 / 僅角色介面 / 不支援）。
4. 點擊有效標籤卡片下方的**複製**按鈕，取得可直接貼入 CaveDuck 的程式碼。

---

1. Open `index.html` and click any card to go to the corresponding tool page.
2. Type in the **search bar** to filter results instantly.
3. Use the **filter buttons** to narrow by support scope (all / both / chat only / creator only / unsupported).
4. Click the **Copy** button on any valid tag's code snippet to get code ready to paste directly into CaveDuck.

---

## 檔案結構 / File Structure

```
/
├── index.html              ← 入口總覽 / Main hub
├── html-tags.html
├── css-props.html
├── svg.html
├── mathml.html
├── animate.html
├── tailwind.html
├── swiper.html
├── css-vars.html
│
└── csv/
    ├── 01_HTML標籤對照表.csv
    ├── 04_tailwind_classes.csv
    ├── 05_swiper_classes.csv
    ├── 06_CSS變數表.csv
    ├── dompurify_tags.csv
    ├── tailwind_classes.csv
    ├── swiper_classes.csv
    └── xss_tag_whitelist.csv
```

---

*Built for CaveDuck platform HTML/CSS authoring.*
