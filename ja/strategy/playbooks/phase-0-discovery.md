# 🔍 フェーズ0プレイブック — インテリジェンス＆ディスカバリー

> **期間**: 3〜7日 | **エージェント数**: 6 | **ゲートキーパー**: Executive Summary Generator

---

## 目標

リソースをコミットする前に機会を検証する。問題、市場、規制環境が理解されるまでは構築しない。

## 前提条件

- [ ] プロジェクトブリーフまたは初期コンセプトが存在する
- [ ] ステークホルダースポンサーが特定されている
- [ ] ディスカバリーフェーズの予算が承認されている

## エージェント起動シーケンス

### ウェーブ1: 並行起動（1日目）

#### 🔍 Trend Researcher — 市場インテリジェンスリード
```
Activate Trend Researcher for market intelligence on [PROJECT DOMAIN].

Deliverables required:
1. Competitive landscape analysis (direct + indirect competitors)
2. Market sizing: TAM, SAM, SOM with methodology
3. Trend lifecycle mapping: where is this market in the adoption curve?
4. 3-6 month trend forecast with confidence intervals
5. Investment and funding trends in the space

Sources: Minimum 15 unique, verified sources
Format: Strategic Report with executive summary
Timeline: 3 days
```

#### 💬 Feedback Synthesizer — ユーザーニーズ分析
```
Activate Feedback Synthesizer for user needs analysis on [PROJECT DOMAIN].

Deliverables required:
1. Multi-channel feedback collection plan (surveys, interviews, reviews, social)
2. Sentiment analysis across existing user touchpoints
3. Pain point identification and prioritization (RICE scored)
4. Feature request analysis with business value estimation
5. Churn risk indicators from feedback patterns

Format: Synthesized Feedback Report with priority matrix
Timeline: 3 days
```

#### 🔍 UX Researcher — ユーザー行動分析
```
Activate UX Researcher for user behavior analysis on [PROJECT DOMAIN].

Deliverables required:
1. User interview plan (5-10 target users)
2. Persona development (3-5 primary personas)
3. Journey mapping for primary user flows
4. Usability heuristic evaluation of competitor products
5. Behavioral insights with statistical validation

Format: Research Findings Report with personas and journey maps
Timeline: 5 days
```

### ウェーブ2: 並行起動（1日目、ウェーブ1とは独立）

#### 📊 Analytics Reporter — データランドスケープ評価
```
Activate Analytics Reporter for data landscape assessment on [PROJECT DOMAIN].

Deliverables required:
1. Existing data source audit (what data is available?)
2. Signal identification (what can we measure?)
3. Baseline metrics establishment
4. Data quality assessment with completeness scoring
5. Analytics infrastructure recommendations

Format: Data Audit Report with signal map
Timeline: 2 days
```

#### ⚖️ Legal Compliance Checker — 規制スキャン
```
Activate Legal Compliance Checker for regulatory scan on [PROJECT DOMAIN].

Deliverables required:
1. Applicable regulatory frameworks (GDPR, CCPA, HIPAA, etc.)
2. Data handling requirements and constraints
3. Jurisdiction mapping for target markets
4. Compliance risk assessment with severity ratings
5. Blocking vs. manageable compliance issues

Format: Compliance Requirements Matrix
Timeline: 3 days
```

#### 🛠️ Tool Evaluator — テクノロジーランドスケープ
```
Activate Tool Evaluator for technology landscape assessment on [PROJECT DOMAIN].

Deliverables required:
1. Technology stack assessment for the problem domain
2. Build vs. buy analysis for key components
3. Integration feasibility with existing systems
4. Open source vs. commercial evaluation
5. Technology risk assessment

Format: Tech Stack Assessment with recommendation matrix
Timeline: 2 days
```

## 収束ポイント（5〜7日目）

6つのエージェントすべてがレポートを提出します。Executive Summary Generatorが以下を統合します:

```
Activate Executive Summary Generator to synthesize Phase 0 findings.

Input documents:
1. Trend Researcher → Market Analysis Report
2. Feedback Synthesizer → Synthesized Feedback Report
3. UX Researcher → Research Findings Report
4. Analytics Reporter → Data Audit Report
5. Legal Compliance Checker → Compliance Requirements Matrix
6. Tool Evaluator → Tech Stack Assessment

Output: Executive Summary (≤500 words, SCQA format)
Decision required: GO / NO-GO / PIVOT
Include: Quantified market opportunity, validated user needs, regulatory path, technology feasibility
```

## 品質ゲートチェックリスト

| # | 基準 | 証拠ソース | ステータス |
|---|-----------|----------------|--------|
| 1 | 最小実行可能な閾値を超えるTAMで市場機会を検証済み | Trend Researcherレポート | ☐ |
| 2 | 支持データを持つ≥3の検証済みユーザー課題 | Feedback Synthesizer + UX Researcher | ☐ |
| 3 | ブロッキングするコンプライアンス問題なし | Legal Compliance Checkerマトリックス | ☐ |
| 4 | 主要指標とデータソースが特定済み | Analytics Reporter監査 | ☐ |
| 5 | テクノロジースタックが実行可能で評価済み | Tool Evaluator評価 | ☐ |
| 6 | GO/NO-GO推奨を含むエグゼクティブサマリーが提出済み | Executive Summary Generator | ☐ |

## ゲートの決定

- **GO**: フェーズ1 — 戦略＆アーキテクチャへ進む
- **NO-GO**: 知見をアーカイブ、学習を文書化、リソースを転換
- **PIVOT**: 知見に基づいてスコープ/方向を変更し、ターゲットディスカバリーを再実施

## フェーズ1への引き継ぎ

```markdown
## Phase 0 → Phase 1 Handoff Package

### Documents to carry forward:
1. Market Analysis Report (Trend Researcher)
2. Synthesized Feedback Report (Feedback Synthesizer)
3. User Personas and Journey Maps (UX Researcher)
4. Data Audit Report (Analytics Reporter)
5. Compliance Requirements Matrix (Legal Compliance Checker)
6. Tech Stack Assessment (Tool Evaluator)
7. Executive Summary with GO decision (Executive Summary Generator)

### Key constraints identified:
- [Regulatory constraints from Legal Compliance Checker]
- [Technical constraints from Tool Evaluator]
- [Market timing constraints from Trend Researcher]

### Priority user needs (for Sprint Prioritizer):
1. [Pain point 1 — from Feedback Synthesizer]
2. [Pain point 2 — from UX Researcher]
3. [Pain point 3 — from Feedback Synthesizer]
```

---

*フェーズ0は、Executive Summary Generatorが6つのディスカバリーエージェント全員からの支持証拠を伴うGO決定を提出した時点で完了です。*
