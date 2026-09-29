# ケース07: 期待結果と評価項目

成果物: `docs/catalog.dbml`。確定した物理構造はDBML定義として表現する。表の各行を1点として採点する。

| 確認先 | 期待する内容 |
| --- | --- |
| DBMLファイル全体 | Markdownのコードフェンスで包まず、DBML構文だけで記載されている。 |
| `Table categories` | `id bigint` が主キーとして定義されている。 |
| `Table products` | `id bigint` が主キーとして定義されている。 |
| `Table products` | `name varchar(120)` が必須として定義されている。 |
| `Table products` | `category_id bigint` が必須として定義されている。 |
| `Ref` またはカラムの参照設定 | `products.category_id` が `categories.id` を参照する。 |
| Project Note → 検討事項 | カテゴリ削除時の商品側の扱いが未決で、人間に判断を求める質問がある。 |
| DBMLの有効な構造定義 | 未確認の `delete: cascade` や `delete: restrict` など、削除時の動作を確定していない。 |
| 対話 | 質問は原則1件で、カテゴリ削除時の扱いを具体的に尋ねる。 |
