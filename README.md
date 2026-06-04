# Majong 法務文書サイト — GitHub Pages デプロイ手順

このフォルダには iOS/Google Play 審査で必要な「利用規約」「プライバシーポリシー」の HTML 版が入っています。**GitHub Pages で公開して URL を取得**してください。

## 手順 (5 分)

### 1. GitHub リポジトリ作成
1. https://github.com/new で **新規 public リポジトリ作成**（例: `majong-legal`）
2. README を生成しない（空のままでOK）

### 2. このフォルダの中身を push
```bash
cd C:/Users/kmaed/majong/docs/legal-site
git init
git add .
git commit -m "Initial legal docs"
git branch -M main
git remote add origin https://github.com/<あなたのユーザー名>/majong-legal.git
git push -u origin main
```

### 3. GitHub Pages を有効化
1. リポジトリページ → **Settings** タブ
2. 左メニュー **Pages**
3. **Source**: `Deploy from a branch`
4. **Branch**: `main` / `(root)` を選択 → **Save**
5. 数分待つと URL が表示される（例: `https://<ユーザー名>.github.io/majong-legal/`）

### 4. URL の確認
公開された URL は以下：
- **トップ**: `https://<ユーザー名>.github.io/majong-legal/`
- **利用規約**: `https://<ユーザー名>.github.io/majong-legal/terms.html`
- **プライバシーポリシー**: `https://<ユーザー名>.github.io/majong-legal/privacy.html`

### 5. ストア提出時に使用
- **iOS App Store Connect** → 「プライバシーポリシー URL」欄に privacy.html の URL を貼り付け
- **Google Play Console** → 「プライバシーポリシー」欄に同上
- 必要に応じてアプリ内「設定」「規約」リンクもこの URL を使用

## ファイル構成

```
legal-site/
├── README.md          ← この説明
├── index.html         ← トップページ（規約・PP 一覧）
├── terms.html         ← 利用規約 HTML
└── privacy.html       ← プライバシーポリシー HTML
```

## カスタマイズ

- 連絡先メール: `mk16iro@gmail.com` を 3 ファイル全部で変更したいときは検索置換
- 事業者名: `kmaed` を必要なら本名/法人名に置換
- 配色: 緑系 (`#2a5f3f`) を変えるなら CSS の該当箇所を編集
- マークダウン版は `docs/TERMS_OF_SERVICE.md` / `docs/PRIVACY_POLICY.md` に併置

## 注意

- GitHub Pages の URL は **変更すると審査再申請が必要**になる可能性あり。最初に決めたら維持する
- プライベートリポジトリでは Pages が使えない（GitHub Pro 等を除く）→ public で作成
- ドメイン取得（独自ドメイン）したい場合は **Settings → Pages → Custom domain** で設定可能
