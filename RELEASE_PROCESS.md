# リリース手順

このリポジトリでは、`ATR Promotion`のmacOS用`.pkg`をGitHub Releaseとして配布します。

## 新版を登録する

1. ソースリポジトリでUnityアプリと`.pkg`を作成し、`verify_lab_pkg.sh`で検証します。
2. `.pkg`のSHA-256を計算します。

   ```bash
   shasum -a 256 "/path/to/ATR-Promotion-X.Y.Z-arm64-lab.pkg"
   ```

3. このリポジトリの`checksums/`と`releases/`へ新しい版の情報を追加します。
4. 変更をコミットし、`vX.Y.Z`タグを作成してpushします。
5. 同じタグのGitHub Releaseを作成し、検証済みの`.pkg`を添付します。

インストーラーのファイル名、Gitタグ、チェックサム、Release添付資産の版番号は必ず一致させてください。

## 重要な制約

- 現在の配布物はApple Silicon（`arm64`）専用です。
- 現在の配布物はDeveloper ID署名・Apple公証をしていない、研究室管理用のパッケージです。
- `.pkg`をGit通常履歴へ直接追加しません。GitHub Releaseへ添付することで、リポジトリのcloneサイズと履歴の肥大化を防ぎます。
