# 🏗️ フェーズ1プレイブック — 戦略＆アーキテクチャ

> **期間**: 5〜10日 | **エージェント数**: 8 | **ゲートキーパー**: Studio Producer + Reality Checker

---

## 目標

1行のコードを書く前に、何を構築するか、どのように構成するか、成功がどのように見えるかを定義する。すべてのアーキテクチャ上の決定を文書化する。すべての機能を優先順位付けする。すべての予算を管理する。

## 前提条件

- [ ] フェーズ0品質ゲートを通過済み（GO決定）
- [ ] フェーズ0引き継ぎパッケージを受領済み
- [ ] プロジェクトスコープについてステークホルダーの整合が取れている

## エージェント起動シーケンス

### ステップ1: 戦略的フレーミング（1〜3日目、並行）

#### 🎬 Studio Producer — 戦略的ポートフォリオ整合
```
Activate Studio Producer for strategic portfolio alignment on [PROJECT].

Input: Phase 0 Executive Summary + Market Analysis Report
Deliverables required:
1. Strategic Portfolio Plan with project positioning
2. Vision, objectives, and ROI targets
3. Resource allocation strategy
4. Risk/reward assessment
5. Success criteria and milestone definitions

Align with: Organizational strategic objectives
Format: Strategic Portfolio Plan Template
Timeline: 3 days
```

#### 🎭 Brand Guardian — ブランドアイデンティティシステム
```
Activate Brand Guardian for brand identity development on [PROJECT].

Input: Phase 0 UX Research (personas, journey maps)
Deliverables required:
1. Brand Foundation (purpose, vision, mission, values, personality)
2. Visual Identity System (colors, typography, spacing as CSS variables)
3. Brand Voice and Messaging Architecture
4. Logo system specifications (if new brand)
5. Brand usage guidelines

Format: Brand Identity System Document
Timeline: 3 days
```

#### 💰 Finance Tracker — 予算とリソース計画
```
Activate Finance Tracker for financial planning on [PROJECT].

Input: Studio Producer strategic plan + Phase 0 Tech Stack Assessment
Deliverables required:
1. Comprehensive project budget with category breakdown
2. Resource cost projections (agents, infrastructure, tools)
3. ROI model with break-even analysis
4. Cash flow timeline
5. Financial risk assessment with contingency reserves

Format: Financial Plan with ROI Projections
Timeline: 2 days
```

### ステップ2: 技術アーキテクチャ（3〜7日目、並行、ステップ1の成果物が揃ってから）

#### 🏛️ UX Architect — 技術アーキテクチャ + UX基盤
```
Activate UX Architect for technical architecture on [PROJECT].

Input: Brand Guardian visual identity + Phase 0 UX Research
Deliverables required:
1. CSS Design System (variables, tokens, scales)
2. Layout Framework (Grid/Flexbox patterns, responsive breakpoints)
3. Component Architecture (naming conventions, hierarchy)
4. Information Architecture (page flow, content hierarchy)
5. Theme System (light/dark/system toggle)
6. Accessibility Foundation (WCAG 2.1 AA baseline)

Files to create:
- css/design-system.css
- css/layout.css
- css/components.css
- docs/ux-architecture.md

Format: Developer-Ready Foundation Package
Timeline: 4 days
```

#### 🏗️ Backend Architect — システムアーキテクチャ
```
Activate Backend Architect for system architecture on [PROJECT].

Input: Phase 0 Tech Stack Assessment + Compliance Requirements
Deliverables required:
1. System Architecture Specification
   - Architecture pattern (microservices/monolith/serverless/hybrid)
   - Communication pattern (REST/GraphQL/gRPC/event-driven)
   - Data pattern (CQRS/Event Sourcing/CRUD)
2. Database Schema Design with indexing strategy
3. API Design Specification with versioning
4. Authentication and Authorization Architecture
5. Security Architecture (defense in depth)
6. Scalability Plan (horizontal scaling strategy)

Format: System Architecture Specification
Timeline: 4 days
```

#### 🤖 AI Engineer — MLアーキテクチャ（該当する場合）
```
Activate AI Engineer for ML system architecture on [PROJECT].

Input: Backend Architect system architecture + Phase 0 Data Audit
Deliverables required:
1. ML System Design
   - Model selection and training strategy
   - Data pipeline architecture
   - Inference strategy (real-time/batch/edge)
2. AI Ethics and Safety Framework
3. Model monitoring and retraining plan
4. Integration points with main application
5. Cost projections for ML infrastructure

Condition: Only activate if project includes AI/ML features
Format: ML System Design Document
Timeline: 3 days
```

#### 👔 Senior Project Manager — 仕様からタスクへの変換
```
Activate Senior Project Manager for task list creation on [PROJECT].

Input: ALL Phase 0 documents + Architecture specs (as available)
Deliverables required:
1. Comprehensive Task List
   - Quote EXACT requirements from spec (no luxury features)
   - Each task has clear acceptance criteria
   - Dependencies mapped between tasks
   - Effort estimates (story points or hours)
2. Work Breakdown Structure
3. Critical path identification
4. Risk register for implementation

Rules:
- Do NOT add features not in the specification
- Quote exact text from requirements
- Be realistic about effort estimates

Format: Task List with acceptance criteria
Timeline: 3 days
```

### ステップ3: 優先順位付け（7〜10日目、逐次、ステップ2の後）

#### 🎯 Sprint Prioritizer — 機能の優先順位付け
```
Activate Sprint Prioritizer for backlog prioritization on [PROJECT].

Input:
- Senior Project Manager → Task List
- Backend Architect → System Architecture
- UX Architect → UX Architecture
- Finance Tracker → Budget Framework
- Studio Producer → Strategic Plan

Deliverables required:
1. RICE-scored backlog (Reach, Impact, Confidence, Effort)
2. Sprint assignments with velocity-based estimation
3. Dependency map with critical path
4. MoSCoW classification (Must/Should/Could/Won't)
5. Release plan with milestone mapping

Validation: Studio Producer confirms strategic alignment
Format: Prioritized Sprint Plan
Timeline: 2 days
```

## 品質ゲートチェックリスト

| # | 基準 | 証拠ソース | ステータス |
|---|-----------|----------------|--------|
| 1 | アーキテクチャが仕様要件の100%をカバー | Senior PMタスクリストとアーキテクチャの相互参照 | ☐ |
| 2 | ブランドシステムの完成（ロゴ、カラー、タイポグラフィ、ボイス） | Brand Guardian成果物 | ☐ |
| 3 | すべての技術コンポーネントに実装パス | Backend Architect + UX Architect仕様 | ☐ |
| 4 | 予算承認済みかつ制約内 | Finance Trackerプラン | ☐ |
| 5 | スプリントプランがベロシティベースで現実的 | Sprint Prioritizerバックログ | ☐ |
| 6 | セキュリティアーキテクチャが定義済み | Backend Architectセキュリティ仕様 | ☐ |
| 7 | コンプライアンス要件がアーキテクチャに統合済み | 技術的決定にマッピングされた法的要件 | ☐ |

## ゲートの決定

**二重承認が必要**: Studio Producer（戦略的）+ Reality Checker（技術的）

- **APPROVED**: 完全なアーキテクチャパッケージを持ってフェーズ2へ進む
- **REVISE**: 特定のアイテムの修正が必要（関連するステップに戻る）
- **RESTRUCTURE**: 根本的なアーキテクチャ上の問題（フェーズ1を再開する）

## フェーズ2への引き継ぎ

```markdown
## Phase 1 → Phase 2 Handoff Package

### Architecture Package:
1. Strategic Portfolio Plan (Studio Producer)
2. Brand Identity System (Brand Guardian)
3. Financial Plan (Finance Tracker)
4. CSS Design System + UX Architecture (UX Architect)
5. System Architecture Specification (Backend Architect)
6. ML System Design (AI Engineer — if applicable)
7. Comprehensive Task List (Senior Project Manager)
8. Prioritized Sprint Plan (Sprint Prioritizer)

### For DevOps Automator:
- Deployment architecture from Backend Architect
- Environment requirements from System Architecture
- Monitoring requirements from Infrastructure needs

### For Frontend Developer:
- CSS Design System from UX Architect
- Brand Identity from Brand Guardian
- Component architecture from UX Architect
- API specification from Backend Architect

### For Backend Architect (continuing):
- Database schema ready for deployment
- API scaffold ready for implementation
- Auth system architecture defined
```

---

*フェーズ1は、Studio ProducerとReality Checkerの両方がアーキテクチャパッケージに承認したときに完了です。*
