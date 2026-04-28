---
name: save-obsidian
description: ユーザーが「ローカルに保存して」「ローカルに記録して」「ローカルにナレッジを残して」などと指示したとき、所定のObsidian Vaultにアクセスしてmdファイルを作成・保存・更新する。
---

# ローカル保存ルール

- **Vault パス（実行環境ごとに使い分ける）**:
  - **WSL / Linux 環境（Claude Code on WSL など）**: `/mnt/c/Users/TakeshiSakurai/Documents/80_Obsidian/DATUM_Valut/`
  - **Windows 環境（Claude Desktop など）**: `C:\Users\TakeshiSakurai\Documents\80_Obsidian\DATUM_Valut\`
  - 上記2つは**同じ実体（Windows 上の同一ディレクトリ）**を指している。実行中の環境に応じて適切な表記を選ぶこと。
  - 判定の目安: `uname` が `Linux` を返す / プラットフォームが `linux` の場合は WSL パス、`win32` などの場合は Windows パス。迷ったら現在の作業ディレクトリ（`pwd`）の形式に合わせる。
  - **混在禁止**: 1つのコマンド・ツール呼び出しの中で WSL パスと Windows パスを混在させない（ファイル書き込みツールはどちらか一方の表記でしか解決できない）。
- **ノート保存先**: 内容に応じて適切なフォルダを選択する
  - `00_Inbox/` — 未整理のメモを一時的に置く場所
  - `10_Daily/` — 日次ノート（Daily Notes）の保存先
  - `20_Notes/` — 学習・思考の永続ノート
  - `30_Projects/` — プロジェクト単位のノート
  - `40_Resources/` — 参考資料・クリッピング
  - `50_1on1/` — 個人ごとの1on1ミーティング記録
  - `Templates/` — テンプレートファイル
- **フォーマット**: Obsidianのfrontmatter（YAML）を必ず付ける
- ノートの作成・編集は **日本語** を基本とする。
- ファイル名は日本語を優先する。スペースは使わず `_` で区切る。内容に適したファイル名にする。

## frontmatterのテンプレート

```yaml
---
title: ノートタイトル
date: YYYY-MM-DD
updated: YYYY-MM-DD hh-mm
tags:
  - タグ1
  - タグ2
category: カテゴリ
status: 完了 | 進行中 | 未着手
---
```
