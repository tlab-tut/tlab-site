# tlab-site
公開Webページです。リロード

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
