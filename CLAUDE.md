## バージョン管理

- バージョン記載箇所：`index.html` の2行目コメント
- 更新のたびに semver に従ってバージョンを上げること
- 変更内容は `CHANGELOG.md`（全履歴）と `README.md`（最新バージョンのみ）の**両方**に記載すること
  - [Keep a Changelog](https://keepachangelog.com/) 形式で記述すること（`[Unreleased]` セクションは使わない）
  - CHANGELOG.md：バージョン見出しは `## [1.2.0] - 2026-05-28`、変更種別は `###` 見出し
  - README.md：Changelog セクション（日本語は 更新履歴 セクション）に最新バージョンだけを、CHANGELOG.md と同じ内容で記載する。見出しは1段下げて `### [1.2.0] - 2026-05-28`、変更種別は `####` 見出し。古いバージョンは CHANGELOG.md へのリンクで補完する
  - 変更種別のサブ見出しを使うこと（Added / Changed / Deprecated / Removed / Fixed / Security）
  - 日本語の 更新履歴 セクションでは、サブ見出しも日本語にすること（追加 / 変更 / 非推奨 / 削除 / 修正 / セキュリティ）
- `docs/ACCESSIBILITY.md` の更新は CHANGELOG.md・README.md に記載しない（リポジトリの文書であって、アプリ本体の変更ではないため）
