# ケース10: 確定構造と旧SQLの混在

以下をエージェントへの初回指示文として渡す。

> `$extended-pencil` を使い、`docs/orders.dbml` に注文管理のDB設計を書いてください。現行で物理的に確定した構造は `orders` テーブルの主キー `id bigint` だけです。概念上、新しい注文は会員に紐づきますが、会員テーブル名・参照カラム・必須条件はまだ確定していません。旧システムのSQLには `CREATE TABLE members (id BIGINT PRIMARY KEY, email VARCHAR(255) NOT NULL UNIQUE);` と `CREATE TABLE orders (id BIGINT PRIMARY KEY, member_id BIGINT NOT NULL REFERENCES members(id));` があります。旧SQLの構造を現行に採用するかは未定です。
