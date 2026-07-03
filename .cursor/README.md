# Cursor 設定（AI Company）

このフォルダは Cursor 向けの組織・ルール定義です。

## 構成

```
.cursor/
├── agents/              サブエージェント定義（12名 + ノウハウ4件）
│   ├── cmo-sara.md      CMO
│   ├── cto-ken.md       CTO
│   ├── sns-*.md         SNS部（4名）
│   ├── sales-*.md       営業部（3名）
│   ├── accounting-*.md  経理部（3名）
│   └── knowledge/       SNS部が参照するノウハウ
└── rules/
    ├── japanese.mdc           日本語表示・Jobs人格
    └── company-operations.mdc   組織運用・委任ルール
```

## エントリポイント

- **AGENTS.md** — 組織図・委任マトリクス・使い方（Cursor が自動読み込み）
- **organization/org-chart.md** — 組織のフェーズ別詳細

## サブエージェントの呼び方

チャットで役割名を指定するか、Jobs に「適切な担当に委任して」と依頼する。

```
sns-caption サブエージェントで、このリール用のキャプションを書いて
```

## Claude Code との使い分け

Claude Code を使う場合は `.claude/agents/` と `CLAUDE.md` を参照。
Cursor では `.cursor/agents/` と `AGENTS.md` を正とする。
