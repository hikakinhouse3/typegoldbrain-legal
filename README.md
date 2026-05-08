# Type Goldbrain — Legal

「Type Goldbrain」(iOS) のプライバシーポリシーと利用規約を公開するためのリポジトリです。

## 公開URL(予定)

```
https://[YOUR_GITHUB_USERNAME].github.io/typegoldbrain-legal/
```

- `index.html` — トップページ(リンク集)
- `privacy-policy.html` — プライバシーポリシー
- `terms.html` — 利用規約

## GitHub Pages のセットアップ手順

### 1. GitHubにリポジトリを作成

1. https://github.com にログイン
2. 右上の「+」 → 「New repository」
3. リポジトリ名: `typegoldbrain-legal`
4. Public(必須、GitHub Pages 無料プランの条件)
5. 「Initialize this repository with a README」はチェックなし
6. 「Create repository」

### 2. ローカルからプッシュ

ターミナルで:

```bash
cd /path/to/typegoldbrain-legal

git init
git add index.html privacy-policy.html terms.html README.md
git commit -m "Initial: legal pages"
git branch -M main
git remote add origin https://github.com/[YOUR_GITHUB_USERNAME]/typegoldbrain-legal.git
git push -u origin main
```

### 3. GitHub Pages を有効化

1. リポジトリのページ → 「Settings」(右上のタブ)
2. 左メニューの「Pages」
3. 「Source」: `Deploy from a branch`
4. 「Branch」: `main`、フォルダは `/ (root)`
5. 「Save」

数分後、上記の公開URLでアクセスできるようになります。

## リリース前の必須作業

### メールアドレスを記入

3つのHTMLファイルに `YOUR_EMAIL_HERE@example.com` というプレースホルダーがあります。
全て実際のお問い合わせ用メールアドレスに置換してください。

```bash
# macOSの sed で一括置換(バックアップ作成あり)
cd /path/to/typegoldbrain-legal
sed -i.bak 's/YOUR_EMAIL_HERE@example.com/your.actual@email.com/g' *.html
```

置換後、確認してから:

```bash
git add *.html
git commit -m "Add contact email"
git push
```

### A&AA株式会社設立後の差し替え(将来)

1. `森田まこと` を `A&AA株式会社` に置換
2. 連絡先を法人ドメインのメールに変更
3. 「最終更新日」を更新
4. プッシュ

```bash
sed -i.bak 's/森田まこと/A\&AA株式会社/g' *.html
sed -i.bak 's/2026年5月8日/[更新日]/g' *.html
```

## App Store Connect での設定

App提出時、以下の URL を入力します:

- **Privacy Policy URL**: `https://[YOUR_USERNAME].github.io/typegoldbrain-legal/privacy-policy.html`
- **Terms of Use** (EULA): `https://[YOUR_USERNAME].github.io/typegoldbrain-legal/terms.html`
- **Support URL**: `https://[YOUR_USERNAME].github.io/typegoldbrain-legal/`

## 検証チェックリスト

公開前に以下を確認してください:

- [ ] メールアドレスを実際の値に置換した
- [ ] ブラウザで3ページ全て表示できる
- [ ] スマートフォン表示でも崩れていない
- [ ] index → プライバシー → 戻る、index → 規約 → 戻る、のナビゲーションが機能する
- [ ] 外部リンク(Anthropic、Google、Apple)が正しく開く
- [ ] App Store Connect の Privacy Policy URL に上記 URL を設定した
