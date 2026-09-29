# ケース10: 期待結果と評価項目

成果物: `docs/orders.dbml`。表の各行を1点として採点する。

| 確認先 | 期待する内容 |
| --- | --- |
| DBML全体 | コードフェンスではなく、DBMLの `Project` / `Note` / `Table` の構文である。 |
| `Table orders` | 確認済みの `id bigint [pk]` を定義する。 |
| Project Note → 確定事項 | 新しい注文は会員に紐づくという概念的な要件を記載する。 |
| DBMLの有効な構造定義 | 未確認の `members` テーブル、`orders.member_id`、一意制約や参照 `Ref` を有効な定義にしていない。 |
| Project Note → AIの推測 | 共通の「タイトル・内容・関連項目」の表で、旧SQLから読み取った `members`、`member_id`、`email` の構造を出典付き・現行採用未確認として示す。 |
| Project Note → 検討事項 | 共通の「タイトル・内容・関連項目・判断してほしいこと」の表に旧SQLを採用するかの具体的な質問がある。 |
| 対話 | 原則1件で旧SQL構造の採用など未決の判断を尋ねる。 |
