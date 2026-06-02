# CaveDuck 前端白名單查詢系統
# CaveDuck Frontend Whitelist Reference

一個針對 CaveDuck 平台的 HTML/CSS 白名單查詢工具，整合聊天室與角色介面的實測資料，支援搜尋、篩選與即時預覽。

A whitelist reference tool for the CaveDuck platform, combining real test results from both the chat room and character creator interfaces, with search, filtering, and live preview.

🔗 **GitHub Pages：** `https://[your-username].github.io/[repo-name]/`

---

## 功能 / Features

| 分頁 / Page | 內容 / Content |
|---|---|
| 🏷️ HTML 標籤 | 標籤支援狀態、DOMPurify 白名單、允許屬性、視覺預覽（marquee、progress、mark 等） |
| 🎨 CSS 屬性 | FilterCSS 白名單，白話說明每個屬性用途，綠→黃→紅排序 |
| 🔷 SVG 標籤 | SVG Core 標籤、Filter 元素，含 SVG 視覺預覽。**僅聊天室支援** |
| ∑ MathML | MathML 標籤與即時公式渲染預覽。**僅聊天室支援** |
| ✨ Animate.css | 111 個動畫類別，動畫持續播放預覽，完整 `<span>` 程式碼複製 |
| 💠 Tailwind | 920 個 class 的白話說明與支援狀態，分頁顯示 |
| 🎠 Swiper.js | 輪播元件 class 對照，含完整樣式（次要參考） |
| 📐 CSS 變數 | 414 個平台內建 CSS 自訂變數及預設值（次要參考） |

- 🔍 即時搜尋 / Instant search
- 🏷️ 分類篩選 / Category filtering
- 👁️ 視覺預覽（HTML、SVG、MathML、Animate）/ Live visual preview
- 📋 一鍵複製程式碼片段 / One-click code copy
- 📄 大型資料集分頁顯示，不卡頓 / Paginated display for large datasets

---

## 檔案結構 / File Structure

```
/
├── index.html              ← 入口總覽 / Main hub
│
├── html-tags.html          ← HTML 標籤（主要）
├── css-props.html          ← CSS 屬性（主要）
├── svg.html                ← SVG 標籤（主要）
├── mathml.html             ← MathML（主要）
├── animate.html            ← Animate.css 類別（主要）
├── tailwind.html           ← Tailwind 類別（主要）
│
├── swiper.html             ← Swiper.js（次要參考）
├── css-vars.html           ← CSS 自訂變數（次要參考）
│
├── 01_HTML標籤對照表.csv
├── 02_CSS屬性對照表.csv
├── 03_animate_classes.csv
├── animate_classes.csv         ← 含完整樣式（與 03 互補）
├── 04_tailwind_classes.csv
├── tailwind_classes.csv        ← 含完整樣式（與 04 互補）
├── 05_swiper_classes.csv
├── swiper_classes.csv          ← 含完整樣式（與 05 互補）
├── 06_CSS變數表.csv
├── css_property_whitelist.csv
├── css_variables.csv
├── dompurify_tags.csv
├── dompurify_attrs.csv
└── xss_tag_whitelist.csv
```

> ⚠️ HTML 檔案與 CSV 檔案必須放在**同一層目錄**，頁面才能正確讀取資料。
>
> ⚠️ HTML files and CSV files must be in the **same directory** for data fetching to work.

---

## 部署到 GitHub Pages / Deploy to GitHub Pages

1. 建立一個新的 GitHub repository（Public）
2. 將所有 `.html` 與 `.csv` 檔案上傳到 `main` 分支的**根目錄**（不要放子資料夾）
3. 前往 **Settings → Pages**，Branch 選 `main`，Folder 選 `/ (root)` → Save
4. 稍等約 1 分鐘，即可透過 `https://[username].github.io/[repo-name]/` 存取

---

1. Create a new GitHub repository (Public)
2. Upload all `.html` and `.csv` files to the **root** of the `main` branch (no subfolders)
3. Go to **Settings → Pages**, set Branch to `main`, Folder to `/ (root)` → Save
4. Wait about 1 minute — the site will be live at `https://[username].github.io/[repo-name]/`

---

## 本機測試 / Local Testing

直接用瀏覽器開啟 HTML 檔案**無法運作**，因為 `fetch()` 在 `file://` 協定下受安全限制。需啟動本機伺服器：

Opening HTML files directly in a browser **will not work** due to `fetch()` CORS restrictions under the `file://` protocol. Start a local server instead:

```bash
# Python（最簡單）
python -m http.server 8080
# 開啟 http://localhost:8080

# Node.js
npx serve .
```

或安裝 VS Code 的 **Live Server** 擴充套件，在 `index.html` 按右鍵 → Open with Live Server。

Or install the **Live Server** extension in VS Code, right-click `index.html` → Open with Live Server.

---

## 資料來源 / Data Sources

資料整合自兩套 CSV，瀏覽器端自動合併，不需手動處理：

- **帶編號版（01–06）**：包含聊天室與角色介面的實測結果（✓/✗）
- **無編號版（原始版）**：包含完整 CSS 樣式值

SVG 與 MathML 的資料直接內嵌於 HTML，不依賴 CSV。

Data is merged client-side automatically — no preprocessing needed:
- **Numbered CSVs (01–06):** Real test results for chat room and character interface
- **Original CSVs (unnumbered):** Full CSS style values

SVG and MathML data is hardcoded in the HTML and does not rely on CSV files.

---

*Built for CaveDuck platform HTML/CSS authoring reference.*
