# extended-pencil

人間とAIエージェントが対話しながら、確定した内容を積み上げてMarkdown文書を作るスキルです。確定事項、AIの推測、検討事項を分けて記録し、未決事項を原則1件ずつ確認します。

## 使い方

`SKILL.md` をスキルとして利用し、作りたい文書の主題と分かっている要件を伝えてください。エージェントは文書を作成または更新し、次に判断が必要な点を尋ねます。回答すると、確認された内容が文書へ反映されます。

要件定義、DB設計、画面設計、API設計では `assets/templates/` の対応する雛形を使用します。その他の文書でも、同じ3章構成で進められます。

## 構成

- `SKILL.md`: 共通の進め方とテンプレートの選択
- `assets/templates/requirements.md`: 要件定義
- `assets/templates/database.md`: DB設計
- `assets/templates/screen.md`: 画面設計
- `assets/templates/api.md`: API設計
