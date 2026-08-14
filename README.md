# Crypto Radar Mobile V1

這是可安裝式 PWA（Progressive Web App），介面針對 iPhone / Android 手機設計。

## 已完成
- Binance USDⓈ-M USDT 永續合約掃描
- 24H 成交額篩選
- 15m / 1h 價格動能
- 5m 爆量倍率
- OI 15m / 1h
- Taker Buy/Sell Ratio
- Funding Rate
- RSI / EMA
- LONG / SHORT / WATCH 評分
- 自選幣
- 本機快取
- Binance 多 API host fallback
- 請求 timeout / failure handling
- PWA manifest / service worker
- iPhone safe-area 與加入主畫面 UI

## iPhone 真正「加入主畫面」需要什麼
PWA 必須由 HTTPS 網址提供。直接從 Files App 點開 index.html 只能作為檔案預覽，
Safari 的 Service Worker / 安裝能力不一定會完整啟用。

可部署到任一 HTTPS 靜態網站服務（例如 GitHub Pages、Cloudflare Pages、Netlify）。
部署後 Safari 開網址 → 分享 → 加入主畫面。

## 本機測試
在資料夾內：

```bash
python -m http.server 8080
```

再用瀏覽器開：
http://localhost:8080

## 重要
此版本不自動下單、不需要 API Key。
市場資料讀取依賴 Binance 公開 API。如果使用者所在網路封鎖 Binance 或 Binance 限流，
App 會明確顯示錯誤，並在存在快取時顯示「非即時」舊資料，不會偽造即時行情。
