# データベース

SQLiteのinstance/photo_share.sqlite3をPeeweeで扱う。外部キー制約を有効にする。
DBには写真本体を入れず、uploads/内の生成したファイル名を保存する。

- User: id、username（表示名）、email（小文字・一意）、password_hash、created_at。
- Post: id、user（Userへの外部キー）、image_filename（一意）、caption、created_at。
- Like: id、user、post。userとpostの組み合わせを一意にする。
- Comment: id、user、post、body、created_at。

Post削除時はLikeとCommentを外部キーのON DELETE CASCADEで削除する。
写真ファイルはアプリが削除する。起動時に存在しないテーブルだけ作る。
DB接続はリクエスト開始時に開き、終了時に閉じる。
日時はUTCで保存し、画面では日本時間で表示する。
