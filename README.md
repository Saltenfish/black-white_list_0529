# CaveDuck 前端白名單查詢系統
# CaveDuck Frontend Whitelist Reference

一個針對 CaveDuck 平台的 HTML/CSS 白名單查詢工具，整合聊天室與角色介面的實測資料，支援搜尋、篩選與即時預覽。

A whitelist reference tool for the CaveDuck platform, combining real test results from both the chat room and character creator interfaces, with search, filtering, and live preview.

🔗 **GitHub Pages：** `https://saltenfish.github.io/black-white_list_0529/`

---

## 頁面說明 / Pages

### 🏷️ HTML 標籤 `html-tags.html`

列出 137 個 HTML 標籤在 CaveDuck 兩種介面的實測結果。

Lists 137 HTML tags with real test results across both CaveDuck interfaces.

| 欄位 / Column | 說明 / Description |
|---|---|
| 聊天室實測 | 標籤在聊天室（開場白/對話）中是否有效 |
| 角色介面實測 | 標籤在角色介紹頁面中是否有效 |
| DOMPurify | 是否列於 DOMPurify 白名單 |
| xss 白名單 | 是否列於 xss 套件白名單 |
| xss 允許屬性 | 該標籤在 xss 套件中允許的屬性 |

每個有效標籤都附有**視覺預覽**與**可複製的程式碼範例**。

Each valid tag includes a **live visual preview** and **copyable code snippet**.

> 💡 顏色邊框代表支援範圍：綠色 = 兩者皆可，黃色 = 僅聊天室，藍色 = 僅角色介面，紅色 = 不支援
>
> 💡 Border color indicates scope: green = both, yellow = chat only, blue = character page only, red = unsupported

---

### 🎨 CSS 屬性 `css-props.html`

列出 inline `style=""` 可使用的 CSS 屬性，分三個層級顯示。

Lists all CSS properties available in inline `style=""`, sorted by support level.

| 層級 / Level | 說明 / Description |
|---|---|
| 🟢 兩者皆可 | 聊天室與角色介面均支援 |
| 🟡 僅聊天室 | 聊天室支援（DOMPurify 不過濾 inline style） |
| 🔴 不支援 | FilterCSS 過濾，兩者均不可用 |

> 💡 **聊天室**的 inline style 幾乎不受限制；**角色介面**僅支援 FilterCSS 白名單內的屬性。
>
> 💡 The **chat room** allows nearly all inline styles; the **character page** is limited to FilterCSS-whitelisted properties.

---

### 🔷 SVG 標籤 `svg.html`

列出 SVG Core 標籤與 Filter 濾鏡元素，含 SVG 視覺預覽。

Lists SVG core tags and filter elements with live SVG previews.

> ⚠️ **僅聊天室支援** — 角色介面會過濾 SVG 內容。
>
> ⚠️ **Chat room only** — the character page strips SVG content.

---

### ∑ MathML `mathml.html`

列出 MathML 數學標記標籤，含即時公式渲染預覽。

Lists MathML tags with live formula rendering previews.

> ⚠️ **僅聊天室支援** — 角色介面不渲染 MathML。
>
> ⚠️ **Chat room only** — the character page does not render MathML.

---

### ✨ Animate.css `animate.html`

列出 111 個 Animate.css 動畫類別，動畫持續播放預覽，提供完整 `<span class="animate__animated animate__xxx">` 程式碼複製。

Lists 111 Animate.css animation classes with live looping previews and full copyable `<span>` code.

---

### 💠 Tailwind `tailwind.html`

920 個 Tailwind CSS class 的白話說明與支援狀態，分頁顯示避免卡頓。

920 Tailwind CSS classes with plain-language descriptions and support status, paginated for performance.

---

### 🎠 Swiper.js `swiper.html`

Swiper.js 輪播元件的 class 對照表（次要參考）。

Swiper.js carousel component class reference (secondary reference).

---

### 📐 CSS 變數 `css-vars.html`

414 個 CaveDuck 平台內建的 CSS 自訂變數及其預設值（次要參考）。

414 built-in CSS custom variables of the CaveDuck platform with default values (secondary reference).

---

## 使用方式 / How to Use

1. 開啟 `index.html` 作為入口，點擊任一分頁卡片進入對應工具。
2. 使用頂部**搜尋欄**輸入關鍵字即時篩選。
3. 使用**篩選按鈕**依支援範圍過濾（兩者皆可 / 僅聊天室 / 僅角色介面 / 不支援）。
4. 點擊有效標籤的**預覽區**下方程式碼右側的「複製」按鈕，直接貼入 CaveDuck。

---

1. Open `index.html` as the entry point and click any card to navigate to a tool.
2. Use the **search bar** at the top to filter results in real time.
3. Use the **filter buttons** to narrow by support scope (both / chat only / creator only / unsupported).
4. Click the **Copy** button next to the code snippet under any valid tag's preview, then paste directly into CaveDuck.

---

## 檔案結構 / File Structure

```
/
├── index.html              ← 入口總覽 / Main hub
├── html-tags.html          ← HTML 標籤
├── css-props.html          ← CSS 屬性
├── svg.html                ← SVG 標籤（僅聊天室）
├── mathml.html             ← MathML（僅聊天室）
├── animate.html            ← Animate.css 類別
├── tailwind.html           ← Tailwind 類別
├── swiper.html             ← Swiper.js（次要）
├── css-vars.html           ← CSS 自訂變數（次要）
│
└── csv/
    ├── 01_HTML標籤對照表.csv     ← HTML 標籤實測結果
    ├── 04_tailwind_classes.csv   ← Tailwind 支援狀態
    ├── 05_swiper_classes.csv     ← Swiper class 對照
    ├── 06_CSS變數表.csv          ← CSS 變數清單
    ├── dompurify_tags.csv        ← DOMPurify 標籤白名單
    ├── tailwind_classes.csv      ← Tailwind 完整樣式
    ├── swiper_classes.csv        ← Swiper 完整樣式
    └── xss_tag_whitelist.csv     ← xss 套件標籤白名單
```

---

## 本機測試 / Local Testing

直接用瀏覽器開啟 HTML 檔案**無法運作**，因為 `fetch()` 在 `file://` 協定下受安全限制。需啟動本機伺服器：

Opening HTML files directly in a browser **will not work** due to `fetch()` CORS restrictions under the `file://` protocol. Start a local server instead:

```bash
# Python
python -m http.server 8080

# Node.js
npx serve .
```

或安裝 VS Code 的 **Live Server** 擴充套件，在 `index.html` 按右鍵 → Open with Live Server。

Or install the **Live Server** extension in VS Code, right-click `index.html` → Open with Live Server.

---

*Built for CaveDuck platform HTML/CSS authoring.*
