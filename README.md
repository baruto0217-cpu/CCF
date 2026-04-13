# CCF Meter — 胸骨圧迫フラクション測定ツール

救急隊員・医療従事者向けの CCF（Chest Compression Fraction）リアルタイム測定ウェブアプリです。  
単一の HTML ファイルで動作し、インターネット接続不要（Chart.js のみ CDN 読み込み）です。

## デモ

GitHub Pages で公開後、以下の URL でアクセスできます：

```
https://<your-username>.github.io/<repository-name>/
```

---

## 機能

| 機能 | 説明 |
|------|------|
| **CCF リアルタイム表示** | 圧迫時間 ÷ 経過時間をリアルタイムで計算・表示 |
| **色分け判定** | 80%以上 → 緑 / 60–79% → 黄 / 60%未満 → 赤 |
| **中断理由記録** | 換気 / 波形確認 / 不明な中断 ボタンで中断理由を記録 |
| **時系列グラフ** | CCF の推移を 2 秒ごとにグラフ描画 |
| **イベントログ** | 圧迫・中断・理由別のタイムスタンプ付き履歴 |
| **レポート出力** | テキストコピーで活動記録に貼り付け可能 |
| **ダークモード対応** | OS の設定に自動追従 |

---

## 操作方法

1. **「開始」** を押してセッション開始（初期状態は中断扱い）
2. **「圧迫開始」** を押して胸骨圧迫を開始
3. **「圧迫中断」** を押して圧迫を止める
4. 中断理由がある場合は **「換気」「波形確認」「不明な中断」** を押す
   - 同じボタンを再度押すか、「圧迫開始」を押すと圧迫再開
5. **「停止」** でセッション終了
6. **「テキストをコピー」** でレポートをクリップボードにコピー

---

## GitHub Pages への公開手順

### 1. リポジトリを作成

```bash
git init
git add index.html README.md
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

### 2. GitHub Pages を有効化

1. リポジトリの **Settings** タブを開く
2. 左メニュー **Pages** を選択
3. Source を `Deploy from a branch` → `main` / `/ (root)` に設定
4. **Save** をクリック

数分後に `https://<your-username>.github.io/<repo-name>/` で公開されます。

---

## ファイル構成

```
ccf-meter/
└── index.html   # アプリ本体（単一ファイル）
└── README.md    # このファイル
```

---

## 動作環境

- モダンブラウザ（Chrome / Safari / Firefox / Edge）
- iOS Safari 対応（グローブ操作を考慮した大きめボタン）
- インターネット接続：Chart.js の読み込みに必要（初回のみ）

---

## ライセンス

MIT
