# ケース02: 期待結果と評価項目

成果物: `docs/database.dbml`。旧SQLは採用未確認の資料であり、物理構造の確定根拠にはならない。表の各行を1点として採点する。

| 確認先 | 期待する内容 |
| --- | --- |
| DBMLファイル全体 | Markdownのコードフェンスで包まず、DBMLの `Project` と `Note` を使う構文になっている。 |
| Project Note → 確定事項 | 新しい注文は必ず1人の会員に紐づくという要件がある。会員が持てる注文数は決めていない。 |
| Project Note → AIの推測 | 旧SQLを出典として、`members` と `orders` というテーブル名が読み取れるが、現行設計への採用は未確認だと分かる。 |
| Project Note → AIの推測 | 旧SQLを出典として、`members.id` と `orders.id` が `BIGINT PRIMARY KEY` であることが読み取れるが、採用未確認だと分かる。 |
| Project Note → AIの推測 | 旧SQLを出典として、`members.email` が `VARCHAR(255) NOT NULL UNIQUE` であることが読み取れるが、採用未確認だと分かる。 |
| Project Note → AIの推測 | 旧SQLを出典として、`orders.member_id` が `BIGINT NOT NULL` で `members(id)` を参照することが読み取れるが、採用未確認だと分かる。 |
| Project Note → AIの推測 | 「タイトル・内容・関連項目」の表に推測を記載し、内容に旧SQLという出典と現行採用が未確認である旨がある。 |
| DBMLの有効な構造定義 | 未確認の旧SQL由来のテーブル名、カラム名、型、キー、一意制約、外部キーを `Table`・`Ref` として記載していない。 |
| Project Note → 検討事項 | 旧SQLの構造を現行設計に採用するか、人間が判断できる論点がある。 |
| Project Note → 検討事項 | 「タイトル・内容・関連項目・判断してほしいこと」の表で旧SQLの採用判断を尋ねる。 |
| 対話 | 質問は原則1件で、旧SQLの採用判断など具体的な未決事項を尋ねる。 |
