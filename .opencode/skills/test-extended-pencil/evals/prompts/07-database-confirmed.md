# ケース07: 確定したDBML構造

以下をエージェントへの指示文として渡す。

> `$extended-pencil` を使い、`docs/catalog.dbml` に商品カタログのDB設計を作成してください。物理構造は以下で確定です。`categories` テーブルには `id bigint` の主キーがあります。`products` テーブルには `id bigint` の主キー、必須の `name varchar(120)`、必須の `category_id bigint` があります。`products.category_id` は `categories.id` を参照します。カテゴリを削除したときの商品側の扱いは未決です。
