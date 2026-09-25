# ATR Promotion Installer

ATR Promotion（IMUを用いた乳児人形姿勢推定システム）の、研究室管理用macOSインストーラー配布リポジトリです。

このリポジトリでは、各版のチェックサム・対応環境・更新履歴をGitタグで管理します。実際の`.pkg`は、対応するGitHub Releaseの添付ファイルとして配布します。これにより、インストーラー本体を通常のGit履歴へ繰り返し保存して履歴を肥大化させずに、版ごとのダウンロードと追跡を可能にします。

## 最新版

- バージョン: `v1.0.6`
- 対象: Apple Silicon（`arm64`）、macOS 11以降
- ファイル: `ATR-Promotion-1.0.6-arm64-lab.pkg`
- SHA-256: `1549147917e523a6e6b360c7632327cc747dfb412f429c5327e300ad935cefc8`

インストーラーは[Releases](https://github.com/tsubame556/ATR-Promotion-Installer/releases)から取得してください。

## インストール

1. 対象Macで`ATR Promotion`を終了します。
2. Releaseから`.pkg`をダウンロードします。
3. 必要に応じてダウンロードしたファイルを検証します。

   ```bash
     shasum -a 256 "/path/to/ATR-Promotion-1.0.6-arm64-lab.pkg"
   ```

4. 管理者権限でインストールします。

   ```bash
   sudo /usr/sbin/installer \
     -pkg "/path/to/ATR-Promotion-1.0.5-arm64-lab.pkg" \
     -target /
   ```

5. `/Applications/ATR Promotion.app`を起動し、Bluetooth利用の許可を与えます。TSND151のペアリングはアプリ内の`センサーペアリング`画面から実行してください。

> [!WARNING]
> この研究室向けパッケージはDeveloper ID署名およびApple公証を行っていません。Gatekeeperの警告が出た場合は、警告を閉じてから **システム設定 → プライバシーとセキュリティ → このまま開く** を使用してください。Gatekeeper全体を無効化したり、回避コマンドを実行したりしないでください。

## 取扱説明書

- [ATR Promotion 取扱説明書 v01（PDF）](manuals/ATR_Promotion_取り扱い説明書_v01.pdf)

## バージョン管理方針

- 各配布版はGitタグ（例: `v1.0.5`）とGitHub Releaseで対応付けます。
- `checksums/`には配布パッケージのSHA-256を保存します。
- `releases/`には版ごとの対応環境・ファイル名・ハッシュを保存します。
- `.pkg`本体はRelease添付資産として保存します。通常のGitコミットへ直接追加しません。

ソースコードは [ATR-Promotions-module](https://github.com/tsubame556/ATR-Promotions-module) で管理しています。
