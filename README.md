# extended-pencil

対話しながら、確定事項・AIの推測・検討事項を分けて文書を作るスキルです。汎用文書のほか、要件定義・DB設計・画面設計・API設計に対応しています。

## 導入

```bash
npx skills add nishimura-yuma77/extended-pencil --skill extended-pencil -g
```

インストール先のエージェントは実行時に選択できます。

## 使い方

作りたい文書と分かっていることを伝えてください。未決の点は原則1件ずつ確認し、回答を文書に反映します。要件定義で基本設計へ持ち越す論点は、そのように指示すると「基本設計への申し送り」にまとめられます。

## 改善時の確認

開発用の評価ケースは [`.opencode/skills/test-extended-pencil/evals/`](.opencode/skills/test-extended-pencil/evals/README.md) にあります。

## 構成

- `SKILL.md`: 共通の進め方
- `assets/templates/global.md`: 汎用文書のテンプレート
- `assets/templates/spec/`: 要件定義・DB設計・画面設計・API設計のテンプレート
