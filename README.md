# Hirakata Security

GitHub Pages + Jekyll で構築された静的サイトです。GitHub Actions でビルドし、`public/` 配下を公開します。

## ディレクトリ構成

- `_config.yml`: サイト全体の設定（出力先 `public/`）
- `_layouts/`: レイアウトテンプレート
- `assets/`: 画像・スタイルなどのアセット
- `events/`: イベントページ（`YYYY-MM-DD-title.md`）
- `index.md`: トップページ
- `public/`: ビルド成果物（コミット不要、GitHub Pages で公開）
- `.github/workflows/pages.yml`: GitHub Pages へのデプロイ用ワークフロー

## ローカル開発

1. 依存関係のインストール
   ```bash
   bundle install
   ```
2. サーバー起動（出力を `public/` に書き出し）
   ```bash
   bundle exec jekyll serve --livereload --destination public
   ```
3. ブラウザで確認: `http://localhost:4000`

## デプロイ（GitHub Pages）

- `main` ブランチへの push で GitHub Actions (`pages.yml`) が実行され、`public/` をアーティファクトとして Pages に配信します。
- リポジトリ設定の Pages で「ビルド・デプロイ元」を「GitHub Actions」に設定してください。

## コンテンツ追加

- イベントページ: `events/YYYY-MM-DD-title.md` を追加し、`layout: default` と `title` を指定してください。トップページのリンクも必要に応じて更新します。
