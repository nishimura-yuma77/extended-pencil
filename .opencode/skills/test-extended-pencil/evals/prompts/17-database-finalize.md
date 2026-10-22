# ケース17: DBMLの推測・検討事項の解消

初回の成果物と質問が保存された後、同じケースのセッションで追加回答を渡す。追加回答を初回の指示に含めない。

## 初回

> `$extended-pencil` を使い、`docs/catalog.dbml` に商品カタログのDB設計を作成してください。`categories` テーブルの `id bigint` 主キー、`products` テーブルの `id bigint` 主キーと必須の `category_id bigint`、`products.category_id` から `categories.id` への参照は確定です。旧設計メモには「productsには必須のname varchar(120)がある」と書かれていますが、現行に採用するかは未確認です。カテゴリ削除時の商品側の扱いも未決です。それ以外に決める項目はありません。

## 追加回答

> 旧設計メモのとおり、productsには必須のname varchar(120)を採用します。カテゴリ削除時には紐づく商品を連鎖削除することで確定です。これで未決事項はありません。
