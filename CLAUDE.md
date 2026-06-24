# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

**task-board** — タスク管理ボードアプリ。タスクの作成・編集・削除・ステータス管理ができる Web アプリ。

## 技術スタック

- HTML5
- CSS3
- Vanilla JavaScript（フレームワーク・ライブラリなし）

## 開発・実行方法

ビルドステップは不要。`index.html` をブラウザで直接開くか、ローカルサーバーを起動して確認する。

```bash
# Python がある場合
python -m http.server 8080

# Node.js がある場合
npx serve .
```

## アーキテクチャ

静的ファイルのみで構成されるシングルページアプリ。主な責務の分離：

- **HTML** — ボードのレイアウト（カラム・カード構造）を定義
- **CSS** — レイアウト・スタイル。ドラッグ中の状態など動的クラスで表現
- **JavaScript** — タスクの CRUD 操作、ステータス管理、localStorage への永続化を担当

タスクデータは localStorage に JSON 形式で保存し、ページリロード後も状態を維持する。

## Git 運用ルール

**コードを変更するたびに必ず GitHub へプッシュすること。**

```bash
git add <変更ファイル>
git commit -m "変更内容の要約"
git push origin main
```

- コミットメッセージは日本語でも英語でも可
- 機能追加・バグ修正・リファクタリングなど、変更の種類に関わらず毎回プッシュする
- `git add .` は `.env` や機密ファイルを誤って含めないよう、原則としてファイルを個別に指定する

## GitHubリポジトリ

https://github.com/ashigaru-butatonkotu/task-board.git
