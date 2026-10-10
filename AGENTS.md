# 写真共有アプリの作業ルール

- 日本語で対応し、docs/requirements.md、docs/ai_context.md、docs/database.md、docs/routes.md、docs/coding_rules.mdを先に読む。
- FlaskとPeewee、SQLiteを使用する。カリキュラムに沿い、段階ごとに動作を確認する。
- 本人が承認したv1の範囲で実装・検証する。検索・フォロー・招待制・公開は対象外。
- 既存の変更を保護する。コミット・push・公開は明示的な依頼があった場合のみ行う。
- .venv、uploads、instance、秘密情報をコミットしない。パスワードやセッションキーを出力しない。
- Pythonの実行とパッケージ導入はプロジェクトの.venvを使用する。
- 検証: .venv/bin/python -m unittest discover -s tests -v
