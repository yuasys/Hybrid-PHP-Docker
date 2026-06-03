# Hybrid-PHP-Docker

軽量なローカル開発用のモノリポ構成（PHP/Apache + SQLite バックエンド、Vite + Vue フロントエンド）。

## 構成
- `backend/` — PHP (Apache) と SQLite 用の Dockerfile、アプリソースは `backend/src` に置きます
- `frontend/` — Vite + Vue のソースと Dockerfile
- `db/` — SQLite データベースを配置するための永続ボリューム用ホストディレクトリ
- `compose.yaml` — Docker Compose 定義

## 必要条件
- Docker / Docker Compose
- （オプション）`gh` CLI（GitHub リポジトリ作成時）

## ローカル起動方法
1. イメージをビルドして起動:
```bash
docker compose build
docker compose up
```
または変更を反映して起動する場合:
```bash
docker compose up --build
```

2. ブラウザで確認:
- フロントエンド（Vite）: http://localhost:5173/
- バックエンド（Apache）: http://localhost:8080/

## 開発メモ
- フロントエンドのソースは `frontend/` 内、`index.html` と `src/` にエントリを置いてください。
- バックエンドのドキュメントルートは `backend/src` です。`index.php` または `index.html` を配置してください。
- SQLite データは `db/` に作成されます。`.gitignore` にデータベースファイルを追加済みです。

## Git / GitHub
リポジトリは GitHub にプッシュされています。初回セットアップや README の追記、CI の追加などご要望があれば対応します。
