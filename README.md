# プロジェクト名

<このプロジェクトの目的を1〜2文で>

## セットアップ

<環境構築の手順>

コミット時に OKF の検証を動かすには、pre-commit を入れる。

```bash
uvx pre-commit install
```

## 使い方

<実行方法・成果物の見方>

## 開発

```bash
uv run --no-project --with pyyaml python tools/okf/validate.py .okf --strict   # OKF の検証
```

```bash
# コミット時にフックがファイルを書き換えたら（Failed になる）、
# 修正後のファイルを add してからコミットし直す
git add -u
git commit

# "Stashed changes conflicted with hook auto-fixes... Rolling back fixes..." が出たら、
# 未ステージの変更が自動修正とぶつかっている。ファイルは元に戻っているので、
# 未ステージの変更を先に片付けて（add するか stash する）からコミットし直す
git status
```

CI は GitHub Actions（`.github/workflows/ci.yml`）と GitLab CI（`.gitlab-ci.yml`）の両方を用意している。使わないほうは消してよい。

## ドキュメント

知識ドキュメント（提案・判断・実験・設計・参照）は `.okf/` にあります（Open Knowledge Format）。入口は [.okf/index.md](.okf/index.md)、AI エージェント向けの規約は [AGENTS.md](AGENTS.md) を参照（`CLAUDE.md` はこれを読み込むだけ）。
