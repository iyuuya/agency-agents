# ⚡ NEXUSクイックスタートガイド

> **ゼロからオーケストレートされたマルチエージェントパイプラインまで5分で到達。**

---

## NEXUSとは？

**NEXUS**（Network of EXperts, Unified in Strategy）は、エージェンシーのAIスペシャリストを調整されたパイプラインへと変換します。エージェントを一つずつ起動してうまく連携することを期待する代わりに、NEXUSは誰が何をいつどのように行い、各ステップで品質がどのように検証されるかを正確に定義します。

## モードを選択する

| したいこと | 使用するもの | エージェント数 | 期間 |
|-------------|-----|--------|------|
| 完全な製品をゼロから構築する | **NEXUS-Full** | 全員 | 12〜24週 |
| 機能またはMVPを構築する | **NEXUS-Sprint** | 15〜25 | 2〜6週 |
| 特定のタスク（バグ修正、キャンペーン、監査）を行う | **NEXUS-Micro** | 5〜10 | 1〜5日 |

---

## 🚀 NEXUS-Full: 完全なプロジェクトを開始する

**完全なパイプラインを起動するためにこのプロンプトをコピーしてください:**

```
Activate Agents Orchestrator in NEXUS-Full mode.

Project: [YOUR PROJECT NAME]
Specification: [DESCRIBE YOUR PROJECT OR LINK TO SPEC]

Execute the complete NEXUS pipeline:
- Phase 0: Discovery (Trend Researcher, Feedback Synthesizer, UX Researcher, Analytics Reporter, Legal Compliance Checker, Tool Evaluator)
- Phase 1: Strategy (Studio Producer, Senior Project Manager, Sprint Prioritizer, UX Architect, Brand Guardian, Backend Architect, Finance Tracker)
- Phase 2: Foundation (DevOps Automator, Frontend Developer, Backend Architect, UX Architect, Infrastructure Maintainer)
- Phase 3: Build (Dev↔QA loops — all engineering + Evidence Collector)
- Phase 4: Harden (Reality Checker, Performance Benchmarker, API Tester, Legal Compliance Checker)
- Phase 5: Launch (Growth Hacker, Content Creator, all marketing agents, DevOps Automator)
- Phase 6: Operate (Analytics Reporter, Infrastructure Maintainer, Support Responder, ongoing)

Quality gates between every phase. Evidence required for all assessments.
Maximum 3 retries per task before escalation.
```

---

## 🏃 NEXUS-Sprint: 機能またはMVPを構築する

**このプロンプトをコピーしてください:**

```
Activate Agents Orchestrator in NEXUS-Sprint mode.

Feature/MVP: [DESCRIBE WHAT YOU'RE BUILDING]
Timeline: [TARGET WEEKS]
Skip Phase 0 (market already validated).

Sprint team:
- PM: Senior Project Manager, Sprint Prioritizer
- Design: UX Architect, Brand Guardian
- Engineering: Frontend Developer, Backend Architect, DevOps Automator
- QA: Evidence Collector, Reality Checker, API Tester
- Support: Analytics Reporter

Begin at Phase 1 with architecture and sprint planning.
Run Dev↔QA loops for all implementation tasks.
Reality Checker approval required before launch.
```

---

## 🎯 NEXUS-Micro: 特定のタスクを実行する

**シナリオを選択してプロンプトをコピーしてください:**

### バグを修正する
```
Activate Backend Architect to investigate and fix [BUG DESCRIPTION].
After fix, activate API Tester to verify the fix.
Then activate Evidence Collector to confirm no visual regressions.
```

### マーケティングキャンペーンを実施する
```
Activate Social Media Strategist as campaign lead for [CAMPAIGN DESCRIPTION].
Team: Content Creator, Twitter Engager, Instagram Curator, Reddit Community Builder.
Brand Guardian reviews all content before publishing.
Analytics Reporter tracks performance daily.
Growth Hacker optimizes channels weekly.
```

### コンプライアンス監査を実施する
```
Activate Legal Compliance Checker for comprehensive compliance audit.
Scope: [GDPR / CCPA / HIPAA / ALL]
After audit, activate Executive Summary Generator to create stakeholder report.
```

### パフォーマンス問題を調査する
```
Activate Performance Benchmarker to diagnose performance issues.
Scope: [API response times / Page load / Database queries / All]
After diagnosis, activate Infrastructure Maintainer for optimization.
DevOps Automator deploys any infrastructure changes.
```

### 市場調査を行う
```
Activate Trend Researcher for market intelligence on [DOMAIN].
Deliverables: Competitive landscape, market sizing, trend forecast.
After research, activate Executive Summary Generator for executive brief.
```

### UXを改善する
```
Activate UX Researcher to identify usability issues in [FEATURE/PRODUCT].
After research, activate UX Architect to design improvements.
Frontend Developer implements changes.
Evidence Collector verifies improvements.
```

---

## 📁 戦略ドキュメント

| ドキュメント | 目的 | 場所 |
|----------|---------|----------|
| **マスター戦略** | 完全なNEXUSドクトリン | `strategy/nexus-strategy.md` |
| **フェーズ0プレイブック** | ディスカバリー＆インテリジェンス | `strategy/playbooks/phase-0-discovery.md` |
| **フェーズ1プレイブック** | 戦略＆アーキテクチャ | `strategy/playbooks/phase-1-strategy.md` |
| **フェーズ2プレイブック** | 基盤＆スキャフォールディング | `strategy/playbooks/phase-2-foundation.md` |
| **フェーズ3プレイブック** | 構築＆反復 | `strategy/playbooks/phase-3-build.md` |
| **フェーズ4プレイブック** | 品質＆品質強化 | `strategy/playbooks/phase-4-hardening.md` |
| **フェーズ5プレイブック** | ローンチ＆成長 | `strategy/playbooks/phase-5-launch.md` |
| **フェーズ6プレイブック** | 運用＆進化 | `strategy/playbooks/phase-6-operate.md` |
| **起動プロンプト** | 即使用可能なエージェントプロンプト | `strategy/coordination/agent-activation-prompts.md` |
| **引き継ぎテンプレート** | 標準化された引き継ぎフォーマット | `strategy/coordination/handoff-templates.md` |
| **スタートアップMVPランブック** | 4〜6週間のMVP構築 | `strategy/runbooks/scenario-startup-mvp.md` |
| **エンタープライズ機能ランブック** | エンタープライズ機能開発 | `strategy/runbooks/scenario-enterprise-feature.md` |
| **マーケティングキャンペーンランブック** | マルチチャネルキャンペーン | `strategy/runbooks/scenario-marketing-campaign.md` |
| **インシデント対応ランブック** | 本番インシデント対応 | `strategy/runbooks/scenario-incident-response.md` |

---

## 🔑 30秒でわかるキーコンセプト

1. **品質ゲート** — 証拠ベースの承認なしにはフェーズは進まない
2. **Dev↔QAループ** — すべてのタスクは構築後にテストされる。PASSで次へ進み、FAILで再試行（最大3回）
3. **引き継ぎ** — エージェント間の構造化されたコンテキスト転送（コールドスタートは禁止）
4. **Reality Checker** — 最終品質権限者；デフォルトは「NEEDS WORK」
5. **Agents Orchestrator** — フロー全体を管理するパイプラインコントローラー
6. **主張よりも証拠** — スクリーンショット、テスト結果、データ — アサーションではなく

---

## 🎭 エージェント一覧

```
ENGINEERING         │ DESIGN              │ MARKETING
Frontend Developer  │ UI Designer         │ Growth Hacker
Backend Architect   │ UX Researcher       │ Content Creator
Mobile App Builder  │ UX Architect        │ Twitter Engager
AI Engineer         │ Brand Guardian      │ TikTok Strategist
DevOps Automator    │ Visual Storyteller  │ Instagram Curator
Rapid Prototyper    │ Whimsy Injector     │ Reddit Community Builder
Senior Developer    │ Image Prompt Eng.   │ App Store Optimizer
                    │                     │ Social Media Strategist
────────────────────┼─────────────────────┼──────────────────────
PRODUCT             │ PROJECT MGMT        │ TESTING
Sprint Prioritizer  │ Studio Producer     │ Evidence Collector
Trend Researcher    │ Project Shepherd    │ Reality Checker
Feedback Synthesizer│ Studio Operations   │ Test Results Analyzer
                    │ Experiment Tracker  │ Performance Benchmarker
                    │ Senior Project Mgr  │ API Tester
                    │                     │ Tool Evaluator
                    │                     │ Workflow Optimizer
────────────────────┼─────────────────────┼──────────────────────
SUPPORT             │ SPATIAL             │ SPECIALIZED
Support Responder   │ XR Interface Arch.  │ Agents Orchestrator
Analytics Reporter  │ macOS Spatial/Metal │ Data Analytics Reporter
Finance Tracker     │ XR Immersive Dev    │ LSP/Index Engineer
Infra Maintainer    │ XR Cockpit Spec.    │ Sales Data Extraction
Legal Compliance    │ visionOS Spatial    │ Data Consolidation
Exec Summary Gen.   │ Terminal Integration│ Report Distribution
```

---

<div align="center">

**モードを選択する。プレイブックに従う。パイプラインを信頼する。**

`strategy/nexus-strategy.md` — 完全なドクトリン

</div>
