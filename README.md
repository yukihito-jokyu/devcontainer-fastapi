# devcontainer-fastapi

このプロジェクトは、Devcontainer を使用した FastAPI 開発環境のテンプレートです。
`uv` をパッケージマネージャーとして使用し、快適な開発体験を提供するためのツールや設定が含まれています。

## Docker コンテナ環境

- **ベースイメージ**: Ubuntu 22.04
- **ユーザー**: vscode (sudo 権限あり)
- **パッケージマネージャー**: `uv` (Python), `apt` (System)
- **タスクランナー**: `go-task` (Taskfile)

### シェル環境 (Zsh & Oh My Zsh)

デフォルトシェルとして **Zsh** を採用し、**Oh My Zsh** でカスタマイズされています。
以下のプラグインがプリインストールされており、コマンド入力の効率化を図っています。

- **zsh-autosuggestions**: コマンド履歴に基づいた入力補完
- **zsh-syntax-highlighting**: コマンドのシンタックスハイライト
- **git**: Git コマンドのエイリアスと補完

## Devcontainer 拡張機能

VS Code で開いた際に、以下の拡張機能が自動的にインストールされます。

- **Python 関連**:
  - Python (ms-python.python)
  - Pylance (ms-python.vscode-pylance)
  - Black Formatter (ms-python.black-formatter)
  - isort (ms-python.isort)
- **コード品質・フォーマット**:
  - Prettier (esbenp.prettier-vscode)
  - EditorConfig (editorconfig.editorconfig)
  - Trailing Spaces (shardulm94.trailing-spaces)
  - Code Spell Checker (streetsidesoftware.code-spell-checker)
  - Error Lens (usernamehw.errorlens)
- **視認性・ユーティリティ**:
  - Indent Rainbow (oderwat.indent-rainbow)
  - Git Graph (mhutchie.git-graph)
  - Japanese Language Pack (ms-ceintl.vscode-language-pack-ja)

## Taskfile からの実行手順

このプロジェクトでは、タスクランナーとして `Taskfile` を使用しています。

### サーバーの起動

以下のコマンドを実行すると、FastAPI サーバーが起動します（ホットリロード有効）。

```bash
task run
```

実行内容:

1. "バックエンド起動" を表示
2. `uv run uvicorn main:app --reload` を実行
