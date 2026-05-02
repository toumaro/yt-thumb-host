# yt-thumb-host

YouTube サムネ Before/After 比較用の画像ホスティング repo。
Google Sheets の `IMAGE()` 関数から `https://raw.githubusercontent.com/...` を参照して使う。

## 用途

サムネ改善案を Google Sheets 上で Before/After 並列に表示するため、画像を恒久 URL で配信する。
収録素材は YouTube に既に公開済み（または公開予定）のサムネのみ。

## ディレクトリ規約

| フォルダ | 用途 |
|---|---|
| `after/` | 改善後サムネ（既存サムネを差し替える用） |
| `new-a/` | 新規バリエーション A：顔出し新規パターン |
| `new-b/` | 新規バリエーション B：既存ベースの修正指示書を画像化 |
| `new-c/` | 新規バリエーション C：B 指示を実適用した完成版 |

## ファイル名規約

`{videoId}.png`（YouTube の videoId と完全一致）

例：`after/3IKdI3MYk2U.png`

## URL 規約

```
https://raw.githubusercontent.com/toumaro/yt-thumb-host/main/{folder}/{videoId}.png
```

Google Sheets での使用例：

```
=IMAGE("https://raw.githubusercontent.com/toumaro/yt-thumb-host/main/after/3IKdI3MYk2U.png")
```

## 同期スクリプト

このリポジトリへの画像投入は別プロジェクトの `scripts/sync_thumbnails_to_github.py` から行う。
手動編集は基本不要。
