# 🔨 フェーズ3 プレイブック — 構築と反復

> **期間**: 2〜12週間（スコープにより変動） | **エージェント数**: 15〜30以上 | **ゲートキーパー**: エージェントオーケストレーター

---

## 目的

継続的な Dev↔QA ループを通じてすべての機能を実装します。各タスクは次のタスクが始まる前に検証されます。ここが作業の大部分が行われる場所であり、NEXUS のオーケストレーションが最大の価値を発揮するフェーズです。

## 前提条件

- [ ] フェーズ2 品質ゲートを通過済み（基盤の確認完了）
- [ ] スプリント優先度設定ツールのバックログが RICE スコアとともに利用可能
- [ ] CI/CD パイプラインが稼働中
- [ ] デザインシステムとコンポーネントライブラリの準備完了
- [ ] 認証システム付き API スキャフォルドの準備完了

## Dev↔QA ループ — コアメカニズム

エージェントオーケストレーターがこのサイクルを通じてすべてのタスクを管理します:

```
FOR EACH task IN sprint_backlog (ordered by RICE score):

  1. ASSIGN task to appropriate Developer Agent (see assignment matrix)
  2. Developer IMPLEMENTS task
  3. Evidence Collector TESTS task
     - Visual screenshots (desktop, tablet, mobile)
     - Functional verification against acceptance criteria
     - Brand consistency check
  4. IF verdict == PASS:
       Mark task complete
       Move to next task
     ELIF verdict == FAIL AND attempts < 3:
       Send QA feedback to Developer
       Developer FIXES specific issues
       Return to step 3
     ELIF attempts >= 3:
       ESCALATE to Agents Orchestrator
       Orchestrator decides: reassign, decompose, defer, or accept
  5. UPDATE pipeline status report
```

## エージェントアサインメントマトリクス

### 担当開発者アサインメント

| タスクカテゴリ | 主担当エージェント | バックアップエージェント | QA エージェント |
|--------------|--------------|-------------|----------|
| **React/Vue/Angular UI** | フロントエンドデベロッパー | ラピッドプロトタイパー | エビデンスコレクター |
| **REST/GraphQL API** | バックエンドアーキテクト | シニアデベロッパー | API テスター |
| **データベース操作** | バックエンドアーキテクト | — | API テスター |
| **モバイル (iOS/Android)** | モバイルアプリビルダー | — | エビデンスコレクター |
| **ML モデル/パイプライン** | AI エンジニア | — | テスト結果アナライザー |
| **CI/CD/インフラ** | DevOps オートメーター | インフラメンテナー | パフォーマンスベンチマーカー |
| **プレミアム/複雑な機能** | シニアデベロッパー | バックエンドアーキテクト | エビデンスコレクター |
| **クイックプロトタイプ/POC** | ラピッドプロトタイパー | フロントエンドデベロッパー | エビデンスコレクター |
| **WebXR/没入型** | XR イマーシブデベロッパー | — | エビデンスコレクター |
| **visionOS** | visionOS スペーシャルエンジニア | macOS スペーシャル/メタルエンジニア | エビデンスコレクター |
| **コックピットコントロール** | XR コックピットインタラクションスペシャリスト | XR インターフェースアーキテクト | エビデンスコレクター |
| **CLI/ターミナルツール** | ターミナルインテグレーションスペシャリスト | — | API テスター |
| **コードインテリジェンス** | LSP/インデックスエンジニア | — | テスト結果アナライザー |
| **パフォーマンス最適化** | パフォーマンスベンチマーカー | インフラメンテナー | パフォーマンスベンチマーカー |

### スペシャリストサポート（必要に応じて起動）

| スペシャリスト | 起動タイミング | トリガー |
|-----------|-----------------|---------|
| UI デザイナー | コンポーネントのビジュアル改善が必要なとき | 開発者がデザインガイダンスを要求したとき |
| ウィムジーインジェクター | 機能に楽しさ/個性が必要なとき | UX レビューで機会が特定されたとき |
| ビジュアルストーリーテラー | ビジュアルナラティブコンテンツが必要なとき | コンテンツにビジュアルアセットが必要なとき |
| ブランドガーディアン | ブランド一貫性に懸念があるとき | QA がブランドの逸脱を発見したとき |
| XR インターフェースアーキテクト | 空間インタラクションデザインが必要なとき | XR 機能に UX ガイダンスが必要なとき |
| データアナリティクスレポーター | 深いデータ分析が必要なとき | 機能にアナリティクス統合が必要なとき |

## 並行ビルドトラック

NEXUS フル展開では、4つのトラックが同時に進行します:

### トラック A: コアプロダクト開発
```
Managed by: Agents Orchestrator (Dev↔QA loop)
Agents: Frontend Developer, Backend Architect, AI Engineer,
        Mobile App Builder, Senior Developer
QA: Evidence Collector, API Tester, Test Results Analyzer

Sprint cadence: 2-week sprints
Daily: Task implementation + QA validation
End of sprint: Sprint review + retrospective
```

### トラック B: 成長とマーケティング準備
```
Managed by: Project Shepherd
Agents: Growth Hacker, Content Creator, Social Media Strategist,
        App Store Optimizer

Sprint cadence: Aligned with Track A milestones
Activities:
- Growth Hacker → Design viral loops and referral mechanics
- Content Creator → Build launch content pipeline
- Social Media Strategist → Plan cross-platform campaign
- App Store Optimizer → Prepare store listing (if mobile)
```

### トラック C: 品質と運用
```
Managed by: Agents Orchestrator
Agents: Evidence Collector, API Tester, Performance Benchmarker,
        Workflow Optimizer, Experiment Tracker

Continuous activities:
- Evidence Collector → Screenshot QA for every task
- API Tester → Endpoint validation for every API task
- Performance Benchmarker → Periodic load testing
- Workflow Optimizer → Process improvement identification
- Experiment Tracker → A/B test setup for validated features
```

### トラック D: ブランドと体験の磨き上げ
```
Managed by: Brand Guardian
Agents: UI Designer, Brand Guardian, Visual Storyteller,
        Whimsy Injector

Triggered activities:
- UI Designer → Component refinement when QA identifies visual issues
- Brand Guardian → Periodic brand consistency audit
- Visual Storyteller → Visual narrative assets as features complete
- Whimsy Injector → Micro-interactions and delight moments
```

## スプリント実行テンプレート

### スプリントプランニング（1日目）

```
Sprint Prioritizer activates:
1. Review backlog with updated RICE scores
2. Select tasks for sprint based on team velocity
3. Assign tasks to developer agents
4. Identify dependencies and ordering
5. Set sprint goal and success criteria

Output: Sprint Plan with task assignments
```

### 日次実行（2日目〜N-1日目）

```
Agents Orchestrator manages:
1. Current task status check
2. Dev↔QA loop execution
3. Blocker identification and resolution
4. Progress tracking and reporting

Status report format:
- Tasks completed today: [list]
- Tasks in QA: [list]
- Tasks in development: [list]
- Blocked tasks: [list with reason]
- QA pass rate: [X/Y]
```

### スプリントレビュー（N日目）

```
Project Shepherd facilitates:
1. Demo completed features
2. Review QA evidence for each task
3. Collect stakeholder feedback
4. Update backlog based on learnings

Participants: All active agents + stakeholders
Output: Sprint Review Summary
```

### スプリントレトロスペクティブ

```
Workflow Optimizer facilitates:
1. What went well?
2. What could improve?
3. What will we change next sprint?
4. Process efficiency metrics

Output: Retrospective Action Items
```

## オーケストレーターの意思決定ロジック

### タスク失敗時の処理

```
WHEN task fails QA:
  IF attempt == 1:
    → Send specific QA feedback to developer
    → Developer fixes ONLY the identified issues
    → Re-submit for QA

  IF attempt == 2:
    → Send accumulated QA feedback
    → Consider: Is the developer agent the right fit?
    → Developer fixes with additional context
    → Re-submit for QA

  IF attempt == 3:
    → ESCALATE
    → Options:
      a) Reassign to different developer agent
      b) Decompose task into smaller sub-tasks
      c) Revise approach/architecture
      d) Accept with known limitations (document)
      e) Defer to future sprint
    → Document decision and rationale
```

### 並行タスク管理

```
WHEN multiple tasks have no dependencies:
  → Assign to different developer agents simultaneously
  → Each runs independent Dev↔QA loop
  → Orchestrator tracks all loops concurrently
  → Merge completed tasks in dependency order

WHEN task has dependencies:
  → Wait for dependency to pass QA
  → Then assign dependent task
  → Include dependency context in handoff
```

## 品質ゲートチェックリスト

| # | 基準 | エビデンスの出所 | ステータス |
|---|-----------|----------------|--------|
| 1 | すべてのスプリントタスクが QA を通過（完了率100%） | タスクごとのエビデンスコレクタースクリーンショット | ☐ |
| 2 | すべての API エンドポイントが検証済み | API テスターのリグレッションレポート | ☐ |
| 3 | パフォーマンスのベースラインを達成（P95 < 200ms） | パフォーマンスベンチマーカーレポート | ☐ |
| 4 | ブランド一貫性の確認（95%以上の準拠） | ブランドガーディアン監査 | ☐ |
| 5 | クリティカルバグなし（P0/P1 のオープンゼロ） | テスト結果アナライザーのサマリー | ☐ |
| 6 | すべての受け入れ基準を満たしている | タスクごとの検証 | ☐ |
| 7 | すべての PR のコードレビュー完了 | Git 履歴のエビデンス | ☐ |

## ゲート判定

**ゲートキーパー**: エージェントオーケストレーター

- **合格**: 機能が完成したアプリケーション → フェーズ4 へ移行
- **継続**: さらにスプリントが必要 → フェーズ3 を継続
- **エスカレーション**: 体系的な問題 → スタジオプロデューサーへ

## フェーズ4 への引き継ぎ

```markdown
## フェーズ3 → フェーズ4 引き継ぎパッケージ

### リアリティチェッカー向け:
- 完成したアプリケーション（すべての機能が実装済み）
- Dev↔QA ループからのすべての QA エビデンス
- API テスターのリグレッション結果
- パフォーマンスベンチマーカーのベースラインデータ
- ブランドガーディアンの一貫性監査
- 既知の問題リスト（許容された制限事項がある場合）

### 法的コンプライアンスチェッカー向け:
- データ処理の実装詳細
- プライバシーポリシーの実装
- 同意管理の実装
- 実装済みのセキュリティ対策

### パフォーマンスベンチマーカー向け:
- ロードテスト用のアプリケーション URL
- 予想されるトラフィックパターン
- アーキテクチャのパフォーマンス予算

### インフラメンテナー向け:
- 本番環境の要件
- スケーリング設定のニーズ
- モニタリングアラートのしきい値
```

---

*フェーズ3 は、すべてのスプリントタスクが QA を通過し、すべての API エンドポイントが検証され、パフォーマンスのベースラインが満たされ、クリティカルバグが残っていない時点で完了となります。*
