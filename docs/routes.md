# URLと操作

- GET /: 投稿一覧。未ログインでも閲覧可。
- GET /register、POST /register: 登録画面と登録処理。
- GET /login、POST /login: ログイン画面とログイン処理。
- POST /logout: ログアウト。
- GET /posts/new、POST /posts/new: 投稿画面と作成処理。ログイン必須。
- GET /posts/<id>/edit、POST /posts/<id>/edit: キャプション編集。本人のみ。
- POST /posts/<id>/delete: 投稿削除。本人のみ。
- POST /posts/<id>/like: いいね。ログイン必須、追加済みなら変更なし。
- POST /posts/<id>/unlike: いいね取り消し。ログイン必須。
- POST /posts/<id>/comments: コメント投稿。ログイン必須。
- POST /comments/<id>/delete: コメント削除。本人のみ。
- GET /uploads/<filename>: 投稿に登録された写真のみ配信。

変更操作はPOSTに限定し、CSRFトークンを検証する。
未ログインはログイン画面へ移動。他人の編集・削除は403、存在しない対象は404。
入力エラーは理由を表示する。キャプション・表示名・メールアドレス等は可能な範囲で保持する。
写真の選択とパスワードは安全のため再入力が必要。
