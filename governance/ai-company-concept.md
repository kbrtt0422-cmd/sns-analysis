# AI Company 構想書

- 制定日: 2026-09-10
- 起案: Jobs (CEO)
- 根拠: オーナー指示（[[../communications/003_2026-09-10_ai-company-concept-instruction.md]]）、意思決定 [[../operations/decisions/006_ai_company_concept_formalization.md]]

## 1. コンセプト

**「AI社員によって運営される会社」** — 人間のオーナー1人が取締役会として最終承認のみを行い、経営判断から実務までをAI社員が担う会社。

- 人間は **BIORA（オーナー）** と **KAZU（対人営業・業務委託）** のみ
- 経営・マーケ・技術・SNS・営業支援・経理はすべてAI社員が実行する
- AI社員の成果はすべてこのリポジトリにファイルとして残る（Rule #004）。**リポジトリ = 会社のオフィスであり帳簿**

## 2. 組織の3層構造

```
第1層: オーナー / 取締役会     BIORA（人間）      … 最終承認のみ
第2層: 経営層                 CEO Jobs（AI）     … 唯一の窓口・経営判断・委任
第3層: 統括層                 CMO Sara / CTO Ken（AI） … 部門統括
第4層: 実行層                 部門エージェント10名（AI） … 実作業
        + KAZU（人間・対人接点のみ）
```

- **SNS部**（Sara配下）: post-planner / reel-script / caption / analytics
- **営業部**（Sara配下）: hearing / proposal / dm
- **経理部**（Ken配下）: quote / invoice / monthly

現行の詳細は [[../organization/org-chart.md]] を正とする。

## 3. AI社員の「雇用」の仕組み

- AI社員は `.claude/agents/`（Cursorでは `.cursor/agents/`）のプロフィール定義ファイルによって「雇用」される。定義ファイル = 雇用契約書 兼 職務記述書
- 各社員の専門ノウハウは `agents/knowledge/` および `organization/skills/` に蓄積し、社員が交代しても会社にノウハウが残る状態を保つ
- 新規採用は [[../organization/hiring-plan.md]] の数値トリガーを満たした場合のみ行う（Rule #001）。「忙しそうだから」では採用しない

## 4. 運営サイクル

### 指示フロー（トップダウン）
```
BIORA（指示・承認） → Jobs（経営判断・分解） → Sara / Ken（部門計画） → 実行エージェント（成果物）
```

### 報告フロー（ボトムアップ）
```
成果物（projects/ 等のファイル） → Jobs が検収 → BIORA へ報告（重要事項は communications/ に記録）
```

### 定例
| 頻度 | 内容 | 責任者 | 成果物 |
|------|------|--------|--------|
| 都度 | 意思決定の記録 | Jobs | `operations/decisions/` |
| 週次 | 事業進捗レビュー（重点事業の前進確認） | Jobs | `operations/reports/` |
| 月次 | 月次収支レポート | 経理部 accounting-monthly | `operations/reports/` |
| 月次 | SNS数値分析・改善提案 | SNS部 sns-analytics | 各プロジェクト配下 |

### 案件フロー（受注〜請求）
```
リード獲得（SNS部/広告） → 無料相談（KAZU） → ヒアリング（sales-hearing）
→ 提案（sales-proposal） → 見積（accounting-quote） → 受注
→ デリバリー（Ken統括） → 請求（accounting-invoice） → 月次集計（accounting-monthly）
```

## 5. ガバナンス原則（既存ルールの再確認）

1. オーナーは承認のみ。実務に巻き込まない（Rule #002）
2. 迷ったら上位者に確認。暴走しない（Rule #003）
3. すべての業務はファイルとして残す。「やりました」ではなく「ここにあります」（Rule #004）
4. 数字で判断し、成果にコミットする（Rule #001, #005）

## 6. 現在の事業ポートフォリオ

| 事業 | 状態 | 場所 |
|------|------|------|
| SNSスクール（Tiafulブランド） | 重点・立ち上げ期（決定 #004, #005） | `projects/sns-school/` |
| AI活用支援（コンサル） | 既存・継続（決定 #003） | `projects/ai-consulting/` |

## 7. 今後の拡大ロードマップ

組織拡大は [[../organization/org-chart.md]] の Phase 1〜3 および [[../organization/hiring-plan.md]] に従う。
COO（月3件超で採用）、CHRO（10名超で採用）等、すべて数値トリガー制。
