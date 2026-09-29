# extended-pencil

人間とAIエージェントが対話しながら、確定した内容を積み上げて文書を作るスキルです。DB設計はDBML、その他の文書はMarkdownを使います。確定事項、AIの推測、検討事項を分けて記録し、未決事項を原則1件ずつ確認します。

## 使い方

本体の `SKILL.md` はOpenCode専用ではなく、CodexやClaude Codeなどからも利用できます。作りたい文書の主題と分かっている要件を伝えてください。エージェントは文書を作成または更新し、次に判断が必要な点を尋ねます。回答すると、確認された内容が文書へ反映されます。

汎用文書には `assets/templates/global.md`、要件定義・DB設計・画面設計・API設計には `assets/templates/spec/` の対応する雛形を使用します。どの文書でも確定事項・AIの推測・検討事項を区別し、推測と検討事項の列構成を揃えます。要件定義でユーザーが基本設計へ持ち越すよう指示した論点は「基本設計への申し送り」にまとめ、検討事項が解消されれば申し送りが残っていても要件定義を完了できます。DB設計の確定した構造はDBMLの `Table`・`Ref`、未確認情報や検討事項は `Project Note` に記録します。

リポジトリをクローンした後、利用するエージェントのスキル配置先からクローン先を参照させてください。以下はリポジトリ直下で実行する例です。

```bash
mkdir -p "$HOME/.config/opencode/skills"
ln -s "$PWD" "$HOME/.config/opencode/skills/extended-pencil"  # OpenCode
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD" "$HOME/.agents/skills/extended-pencil"  # Codex
mkdir -p "$HOME/.claude/skills"
ln -s "$PWD" "$HOME/.claude/skills/extended-pencil"  # Claude Code
```

利用するエージェントの2行だけ実行してください。スキル本体はこのリポジトリの `SKILL.md` にあり、各配置先には同じクローンを参照させます。

## 改善時の確認

開発・回帰確認用の `test-extended-pencil` だけは、このリポジトリ専用のOpenCodeプロジェクトスキルです。[`evals/`](.opencode/skills/test-extended-pencil/evals/README.md) に試す指示文と期待結果・評価項目を対で置いています。Taskで文書生成・採点のできるエージェントが利用できる環境では、`$test-extended-pencil` がケースごとに独立したセッションを起動して評価します。生成文書・対話・採点結果は `.opencode/skills/test-extended-pencil/.work/` に保存され、Gitの管理対象から外れます。実際の失敗が見つかったら、そのケースを追加または更新します。

## 構成

- `SKILL.md`: 共通の進め方とテンプレートの選択
- `assets/templates/global.md`: 汎用文書の雛形と共通の記載形式
- `assets/templates/spec/requirements.md`: 要件定義
- `assets/templates/spec/database.dbml`: DB設計
- `assets/templates/spec/screen.md`: 画面設計
- `assets/templates/spec/api.md`: API設計
- `.opencode/skills/test-extended-pencil/`: このリポジトリ専用・OpenCode用の開発評価スキルと、その `evals/` にある評価ケース
