# 🚨 ランブック: インシデント対応

> **モード**: NEXUS-マイクロ | **期間**: 数分〜数時間 | **エージェント数**: 3〜8

---

## シナリオ

本番環境で何かが壊れています。ユーザーに影響が出ています。対応速度が重要ですが、正しく対処することも同様に重要です。このランブックは検知からポストモーテムまでをカバーします。

## 重大度の分類

| レベル | 定義 | 例 | 対応時間 |
|-------|-----------|----------|--------------|
| **P0 — クリティカル** | サービス完全停止、データ損失、セキュリティ侵害 | データベース破損、DDoS 攻撃、認証システム障害 | 即時（全員対応） |
| **P1 — 高** | 主要機能の障害、大幅なパフォーマンス低下 | 決済処理停止、エラー率50%以上、レイテンシ10倍 | < 1時間 |
| **P2 — 中** | 軽微な機能の障害、回避策あり | 検索が動作しない、クリティカルでない API エラー | < 4時間 |
| **P3 — 低** | 外観上の問題、軽微な不便 | スタイリングのバグ、タイポ、軽微な UI の不具合 | 次スプリント |

## 重大度別の対応チーム

### P0 — クリティカル対応チーム
| エージェント | 役割 | アクション |
|-------|------|--------|
| **インフラメンテナー** | インシデントコマンダー | スコープの評価、対応の調整 |
| **DevOps オートメーター** | デプロイメント/ロールバック | 必要に応じたロールバックの実行 |
| **バックエンドアーキテクト** | 根本原因の調査 | システム問題の診断 |
| **フロントエンドデベロッパー** | UI 側の調査 | クライアントサイドの問題の診断 |
| **サポートレスポンダー** | ユーザーへのコミュニケーション | ステータスページの更新、ユーザー通知 |
| **エグゼクティブサマリージェネレーター** | ステークホルダーへのコミュニケーション | リアルタイムのエグゼクティブ更新 |

### P1 — 高対応チーム
| エージェント | 役割 |
|-------|------|
| **インフラメンテナー** | インシデントコマンダー |
| **DevOps オートメーター** | デプロイメントサポート |
| **担当開発エージェント** | 修正の実装 |
| **サポートレスポンダー** | ユーザーへのコミュニケーション |

### P2 — 中対応
| エージェント | 役割 |
|-------|------|
| **担当開発エージェント** | 修正の実装 |
| **エビデンスコレクター** | 修正の確認 |

### P3 — 低対応
| エージェント | 役割 |
|-------|------|
| **スプリント優先度設定ツール** | バックログへの追加 |

## インシデント対応シーケンス

### ステップ1: 検知とトリアージ（0〜5分）

```
TRIGGER: Alert from monitoring / User report / Agent detection

Infrastructure Maintainer:
1. Acknowledge alert
2. Assess scope and impact
   - How many users affected?
   - Which services are impacted?
   - Is data at risk?
3. Classify severity (P0/P1/P2/P3)
4. Activate appropriate response team
5. Create incident channel/thread

Output: Incident classification + response team activated
```

### ステップ2: 調査（5〜30分）

```
PARALLEL INVESTIGATION:

Infrastructure Maintainer:
├── Check system metrics (CPU, memory, network, disk)
├── Review error logs
├── Check recent deployments
└── Verify external dependencies

Backend Architect (if P0/P1):
├── Check database health
├── Review API error rates
├── Check service communication
└── Identify failing component

DevOps Automator:
├── Review recent deployment history
├── Check CI/CD pipeline status
├── Prepare rollback if needed
└── Verify infrastructure state

Output: Root cause identified (or narrowed to component)
```

### ステップ3: 緩和（15〜60分）

```
DECISION TREE:

IF caused by recent deployment:
  → DevOps Automator: Execute rollback
  → Infrastructure Maintainer: Verify recovery
  → Evidence Collector: Confirm fix

IF caused by infrastructure issue:
  → Infrastructure Maintainer: Scale/restart/failover
  → DevOps Automator: Support infrastructure changes
  → Verify recovery

IF caused by code bug:
  → Relevant Developer Agent: Implement hotfix
  → Evidence Collector: Verify fix
  → DevOps Automator: Deploy hotfix
  → Infrastructure Maintainer: Monitor recovery

IF caused by external dependency:
  → Infrastructure Maintainer: Activate fallback/cache
  → Support Responder: Communicate to users
  → Monitor for external recovery

THROUGHOUT:
  → Support Responder: Update status page every 15 minutes
  → Executive Summary Generator: Brief stakeholders (P0 only)
```

### ステップ4: 解決の確認（修正後）

```
Evidence Collector:
1. Verify the fix resolves the issue
2. Screenshot evidence of working state
3. Confirm no new issues introduced

Infrastructure Maintainer:
1. Verify all metrics returning to normal
2. Confirm no cascading failures
3. Monitor for 30 minutes post-fix

API Tester (if API-related):
1. Run regression on affected endpoints
2. Verify response times normalized
3. Confirm error rates at baseline

Output: Incident resolved confirmation
```

### ステップ5: ポストモーテム（48時間以内）

```
Workflow Optimizer leads post-mortem:

1. タイムラインの再構成
   - 問題はいつ発生したか？
   - いつ検知されたか？
   - いつ解決されたか？
   - ユーザーへの影響の合計時間

2. 根本原因分析
   - 何が失敗したか？
   - なぜ失敗したか？
   - なぜ早期に発見されなかったか？
   - 5 Whys 分析

3. 影響評価
   - 影響を受けたユーザー数
   - 収益への影響
   - 評判への影響
   - データへの影響

4. 予防策
   - どのようなモニタリングがあれば早期検知できたか？
   - どのようなテストがあれば防止できたか？
   - どのようなプロセス変更が必要か？
   - どのようなインフラ変更が必要か？

5. アクションアイテム
   - [アクション] → [オーナー] → [期限]
   - [アクション] → [オーナー] → [期限]
   - [アクション] → [オーナー] → [期限]

Output: Post-Mortem Report → Sprint Prioritizer adds prevention tasks to backlog
```

## コミュニケーションテンプレート

### ステータスページ更新（サポートレスポンダー）
```
[TIMESTAMP] — [SERVICE NAME] Incident

Status: [Investigating / Identified / Monitoring / Resolved]
Impact: [Description of user impact]
Current action: [What we're doing about it]
Next update: [When to expect the next update]
```

### エグゼクティブ更新（エグゼクティブサマリージェネレーター — P0 のみ）
```
INCIDENT BRIEF — [TIMESTAMP]

SITUATION: [Service] is [down/degraded] affecting [N users/% of traffic]
CAUSE: [Known/Under investigation] — [Brief description if known]
ACTION: [What's being done] — ETA [time estimate]
IMPACT: [Business impact — revenue, users, reputation]
NEXT UPDATE: [Timestamp]
```

## エスカレーションマトリクス

| 条件 | エスカレーション先 | アクション |
|-----------|------------|--------|
| P0 が 30分以内に解決しない | スタジオプロデューサー | 追加リソース、ベンダーエスカレーション |
| P1 が 2時間以内に解決しない | プロジェクトシェパード | リソースの再配分 |
| データ侵害が疑われる | 法的コンプライアンスチェッカー | 規制通知の評価 |
| ユーザーデータが影響を受ける | 法的コンプライアンスチェッカー + エグゼクティブサマリージェネレーター | GDPR/CCPA 通知 |
| 収益への影響 > $X | ファイナンストラッカー + スタジオプロデューサー | ビジネスインパクト評価 |
