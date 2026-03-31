# AlphaScope v2.3

**AI-Powered Japanese Equity Analysis Platform**

日本株の企業分析ダッシュボード。57社のプリセットデータ + EDINET DB API連携で全上場3,849社の財務データを自動取得。

![AlphaScope](https://img.shields.io/badge/AlphaScope-v2.3-22d3ee?style=flat-square)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square)
![Vite](https://img.shields.io/badge/Vite-6-646CFF?style=flat-square)
![Railway](https://img.shields.io/badge/Deploy-Railway-0B0D0E?style=flat-square)

## Features

- **企業ダッシュボード** — 業績推移(年次/四半期/利益率タブ)、ROE DuPont分解、バリュエーションレンジ
- **AI分析チャット** — Claude API連携のインテリジェント企業分析
- **EDINET DB連携** — APIキー1つで全上場企業の5年分財務データを自動取得
- **一括インポート** — スクリーニング条件で数十社まとめて追加
- **利益急伸スクリーニング** — 営業利益YoY+20億以上の閾値フィルタ
- **企業比較** — 散布図(Rule of 40)、プリセット比較、セクターフィルタ
- **Google風検索** — 自然言語スクリーニング対応

## Quick Start

```bash
# Clone
git clone https://github.com/YOUR_USER/alphascope.git
cd alphascope

# Install & Dev
npm install
npm run dev
# → http://localhost:3000
```

## Deploy to Railway

1. GitHubリポジトリにpush
2. [Railway](https://railway.app) → New Project → Deploy from GitHub repo
3. 自動でビルド＆デプロイ（`railway.json` 設定済み）

環境変数は不要（APIキーはブラウザ上で入力）。

## EDINET DB API 連携

1. https://edinetdb.jp/developers でAPIキー取得（無料）
2. AlphaScope右上の「⚙ 設定」→ APIキー入力
3. 「テスト接続」で確認
4. 以降、銘柄追加時に自動でEDINET DBから取得

**一括インポート**: 設定パネル内のプリセットボタンで条件検索→まとめて追加

## Tech Stack

- **Frontend**: React 18 + Vite 6
- **Styling**: CSS-in-JS (inline styles, Bloomberg-inspired dark theme)
- **AI**: Anthropic Claude API (Web Search対応)
- **Data**: EDINET DB REST API + 57社ハードコードデータ
- **Deploy**: Railway (Nixpacks)

## Project Structure

```
alphascope/
├── index.html          # Entry point
├── src/
│   ├── main.jsx        # React mount
│   └── App.jsx         # Full application (1,250+ lines)
├── package.json
├── vite.config.js
├── railway.json        # Railway deploy config
├── nixpacks.toml       # Nixpacks build config
└── README.md
```

## License

Private / All rights reserved
