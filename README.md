# Common Dev Container

## 1. 概要 (Overview)

このリポジトリは、エコシステム全体で共有される開発環境設定（Dev Container）のテンプレートを管理する中央リポジトリです。
目的は、全てのプロジェクトで一貫性のある、かつ最新の開発ツール（Cursor, CLIツール等）利用体験を提供することです。

管理は、エコシステム統合AIが担当します。

## 2. 利用方法 (Usage)

各プロジェクトは、`git submodule` を利用して、このリポジトリを自身の `.devcontainer/common` ディレクトリに取り込みます。

### 新規プロジェクトへの導入手順

```bash
# 1. プロジェクトのルートディレクトリに移動
cd /path/to/your-project

# 2. .devcontainer ディレクトリを作成
mkdir -p .devcontainer

# 3. このリポジトリを submodule として追加
git submodule add https://github.com/wataru-ito-1/common-dev-container.git .devcontainer/common
```

### 既存プロジェクトの更新手順

共通設定が更新された際は、各プロジェクトのルートで以下のコマンドを実行することで最新版に同期できます。

```bash
# submoduleを最新の状態に更新
git submodule update --remote

# 変更をコミット
git add .devcontainer/common
git commit -m "Update common dev container"
```

## 3. 管理ディレクトリ構造

- `/templates`:
  - `ci/`: CI/CDワークフローのテンプレート
  - `docker/`: Dockerfileのテンプレート
  - `note/`: Obsidianノートのテンプレート
- `(その他)`:
  - Dev Containerの基本設定ファイル (e.g., `Dockerfile.base`) 