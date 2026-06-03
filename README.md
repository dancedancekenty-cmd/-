# Instagram Brand Designer — Netlify デプロイ手順

## 必要なもの
- Anthropic APIキー（https://console.anthropic.com）
- GitHubアカウント
- Netlifyアカウント（無料）

---

## STEP 1：GitHubにアップロード

1. https://github.com にログイン
2. 右上「＋」→「New repository」
3. Repository name: `insta-brand`
4. Public を選択 → 「Create repository」
5. 「uploading an existing file」をクリック
6. このフォルダの中身を全部アップロード
   - index.html
   - netlify.toml
   - netlify/ フォルダ（中の functions/claude.js ごと）
7. 「Commit changes」をクリック

---

## STEP 2：Netlifyに接続

1. https://netlify.com にログイン（GitHubアカウントでOK）
2. 「Add new site」→「Import an existing project」
3. 「GitHub」を選択 → `insta-brand` リポジトリを選択
4. Build settings はそのまま → 「Deploy site」をクリック

---

## STEP 3：APIキーを設定（重要）

1. Netlifyのダッシュボードで「Site settings」
2. 左メニュー「Environment variables」
3. 「Add a variable」をクリック
4. Key: `ANTHROPIC_API_KEY`
5. Value: `sk-ant-xxxx...`（Anthropicのキー）
6. 「Save」→ サイトを再デプロイ

---

## STEP 4：アンケート収集の設定（任意）

1. https://formspree.io にアクセス
2. 無料登録 → 新しいフォームを作成
3. フォームIDをコピー（例：`xabcdefg`）
4. index.html の `YOUR_FORM_ID` を書き換える
   - 変更前: `https://formspree.io/f/YOUR_FORM_ID`
   - 変更後: `https://formspree.io/f/xabcdefg`

---

## 完了！

デプロイ後、Netlifyから発行されたURLを学生に共有するだけです。
例: `https://insta-brand-xxxx.netlify.app`
