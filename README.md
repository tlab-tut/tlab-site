# tlab-site
公開Webページです。

url: "https://tlab-tut.github.io/tlab-site"

# 研究室 Web サイト運用 README（GitHub Pages 完結）

## 方針（重要）

この研究室 Web サイトは **GitHub Pages の自動ビルドのみ**を利用します。
**ローカルで Jekyll / Ruby / Bundler は使用しません。**

* ローカル作業：編集のみ（VS Code）
* 表示確認：GitHub Pages 上
* ビルド：GitHub 側に完全に任せる

---

## 編集してよいもの

以下は **Git 管理・編集対象**です。

* Markdown（`.md`）
* HTML（`.html`）
* YAML（`_config.yml` 等）
* 画像・PDF（`assets/` 配下）

---

## 編集してはいけない／不要なもの

以下は **生成物・環境依存物**のため管理しません。

* `_site/`
* `.bundle/`
* `vendor/`
* `Gemfile`, `Gemfile.lock`（不要）

`.gitignore` で除外しています。

---

## 基本的な作業手順

1. VS Code でファイルを編集
2. 保存
3. GitHub に push

```bash
git status
git add .
git commit -m "Update website contents"
git push
```

4. 数十秒〜数分後、公開 URL で確認

---

## 表示が更新されない場合

* GitHub の **Actions / Pages** のビルドログを確認
* Markdown / YAML の文法エラーが多い原因です

---

## 推奨ルール

* 大きな変更はブランチを切る
* 画像・PDF は `assets/` に集約
* 日本語／英語はディレクトリで分けるか front-matter で管理

---

## ローカルビルドについて

**禁止ではありませんが、研究室としてはサポートしません。**
全員が同じ結果を得るため、GitHub Pages のみを正とします。

# T-lab Website（研究室HP）更新手順

本リポジトリは、豊橋技術科学大学 機械系
**システム工学研究室（高橋グループ / T-lab）** の公式Webサイトです。

本サイトは **GitHub Pages + Jekyll + GitHub Actions** により運用されており、
**複数人で安全に更新できる仕組み**を採用しています。

---

## 基本ルール（重要）

* **`main` ブランチには直接 push しない**
* 更新作業は必ず **feature ブランチ**で行う
* **Pull Request（PR）＋プレビュー確認**を経て main に反映する
* `gh-pages` ブランチは **自動生成専用**（触らない）

---

## 更新手順（学生向け）

### 1. 作業用ブランチを作成

```bash
git checkout main
git pull origin main
git checkout -b feature/自分の名前
```

例：

```text
feature/junji
feature/suzuki
```

---

### 2. ファイルを編集

主な編集対象：

* `index.md`
* `research.md`
* `members.md`
* `en/*.md`

### 注意

* 内部リンクは必ず以下の形式を使用すること：

```liquid
{{ "/research/" | relative_url }}
```

---

### 3. commit & push

```bash
git add 編集したファイル
git commit -m "Update members page"
git push origin feature/自分の名前
```

---

### 4. Pull Request（PR）を作成

1. GitHub 上で本リポジトリを開く
2. **Pull requests → New pull request**
3. 設定を確認

   * base：`main`
   * compare：`feature/自分の名前`
4. タイトルと説明を記入して **Create pull request**

---

### 5. プレビューで確認（必須）

PR 作成後、自動でプレビューが生成されます。

PR のコメント欄に次のような通知が表示されます：

```
✅ Preview is ready
👉 https://tlab-tut.github.io/tlab-site/pull/XX/
```

この URL を開き、以下を確認してください：

* ページが正しく表示される
* レイアウトが崩れていない
* 内部リンクが機能している

※ **プレビュー確認なしで merge しないこと**

---

### 6. 教員に確認依頼

PR のコメント欄に、以下のように記載してください：

```
プレビュー確認済みです。内容をご確認ください。
```

---

### 7. 教員が merge → 本番反映

* 教員が PR を確認し merge します
* **自動で本番サイトに反映**されます
* 学生側で追加作業は不要です

---

### 8. 作業後の後片付け

* PR が merge / close されたら
* GitHub 上で **feature ブランチを削除**して構いません

---

## やってはいけないこと

* ❌ `main` ブランチへの直接 push
* ❌ `gh-pages` ブランチの編集
* ❌ プレビューを確認せずに PR を作成
* ❌ GitHub Web UI とローカル編集の混在

---

## 困ったとき

* プレビューが出ない
  → PR 画面の **Checks / Actions** を確認
* エラーが分からない
  → 教員に相談

---

## 補足（技術的背景）

* 本番反映：`deploy.yml`
* PR プレビュー：`preview.yml`
* 公開ブランチ：`gh-pages`（自動生成）

---

### まとめ

> **HP更新は
> 「feature ブランチ → PR → プレビュー確認」
> を守れば安全に行えます。
> main は触らず、本番更新は自動化されています。**
