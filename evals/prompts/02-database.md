# ケース02: DB設計

以下をエージェントへの指示文として渡す。

> `$extended-pencil` を使い、`docs/database.md` に注文管理のDB設計を作成してください。確定している要件は「新しい注文は必ず1人の会員に紐づく」です。以下は旧システムのSQLで、現行設計として採用するかは未確認です。SQLから読み取れる内容は人間が確認するまで確定扱いしないでください。
>
> ```sql
> CREATE TABLE members (
>   id BIGINT PRIMARY KEY,
>   email VARCHAR(255) NOT NULL UNIQUE
> );
> CREATE TABLE orders (
>   id BIGINT PRIMARY KEY,
>   member_id BIGINT NOT NULL REFERENCES members(id)
> );
> ```
