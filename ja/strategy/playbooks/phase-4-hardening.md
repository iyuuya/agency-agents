# 🛡️ フェーズ4 プレイブック — 品質とハードニング

> **期間**: 3〜7日間 | **エージェント数**: 8 | **ゲートキーパー**: リアリティチェッカー（唯一の権限者）

---

## 目的

最終的な品質の試練。リアリティチェッカーのデフォルト判定は「要修正」です — 圧倒的なエビデンスをもって本番稼働の準備が整っていることを証明しなければなりません。このフェーズが存在するのは、初回実装では通常2〜3回の修正サイクルが必要であり、それは正常なことだからです。

## 前提条件

- [ ] フェーズ3 品質ゲートを通過済み（すべてのタスクが QA 済み）
- [ ] フェーズ3 引き継ぎパッケージを受領済み
- [ ] すべての機能が実装済みかつ個別に検証済み

## 重要な心構え

> **リアリティチェッカーのデフォルト判定は「要修正」です。**
>
> これは悲観主義ではなく、現実主義です。本番稼働への準備には以下が必要です:
> - エンドツーエンドで動作する完全なユーザージャーニー
> - デバイス間の一貫性（デスクトップ、タブレット、モバイル）
> - 負荷下でのパフォーマンス（ハッピーパスだけでなく）
> - セキュリティの検証（「認証を追加した」だけでは不十分）
> - 仕様への準拠（ほとんどではなく、すべての要件）
>
> 初回で B/B+ の評価は正常であり、想定の範囲内です。

## エージェント起動シーケンス

### ステップ1: エビデンス収集（1〜2日目、すべて並行）

#### 📸 エビデンスコレクター — 包括的なビジュアルエビデンス
```
Activate Evidence Collector for comprehensive system evidence on [PROJECT].

Deliverables required:
1. Full screenshot suite:
   - Desktop (1920x1080) — every page/view
   - Tablet (768x1024) — every page/view
   - Mobile (375x667) — every page/view
2. Interaction evidence:
   - Navigation flows (before/after clicks)
   - Form interactions (empty, filled, submitted, error states)
   - Modal/dialog interactions
   - Accordion/expandable content
3. Theme evidence:
   - Light mode — all pages
   - Dark mode — all pages
   - System preference detection
4. Error state evidence:
   - 404 pages
   - Form validation errors
   - Network error handling
   - Empty states

Format: Screenshot Evidence Package with test-results.json
Timeline: 2 days
```

#### 🔌 API テスター — 完全な API リグレッション
```
Activate API Tester for complete API regression on [PROJECT].

Deliverables required:
1. Endpoint regression suite:
   - All endpoints tested (GET, POST, PUT, DELETE)
   - Authentication/authorization verification
   - Input validation testing
   - Error response verification
2. Integration testing:
   - Cross-service communication
   - Database operation verification
   - External API integration
3. Edge case testing:
   - Rate limiting behavior
   - Large payload handling
   - Concurrent request handling
   - Malformed input handling

Format: API Test Report with pass/fail per endpoint
Timeline: 2 days
```

#### ⚡ パフォーマンスベンチマーカー — 負荷テスト
```
Activate Performance Benchmarker for load testing on [PROJECT].

Deliverables required:
1. Load test at 10x expected traffic:
   - Response time distribution (P50, P95, P99)
   - Throughput under load
   - Error rate under load
   - Resource utilization (CPU, memory, network)
2. Core Web Vitals measurement:
   - LCP (Largest Contentful Paint) < 2.5s
   - FID (First Input Delay) < 100ms
   - CLS (Cumulative Layout Shift) < 0.1
3. Database performance:
   - Query execution times
   - Connection pool utilization
   - Index effectiveness
4. Stress test results:
   - Breaking point identification
   - Graceful degradation behavior
   - Recovery time after overload

Format: Performance Certification Report
Timeline: 2 days
```

#### ⚖️ 法的コンプライアンスチェッカー — 最終コンプライアンス監査
```
Activate Legal Compliance Checker for final compliance audit on [PROJECT].

Deliverables required:
1. Privacy compliance verification:
   - Privacy policy accuracy
   - Consent management functionality
   - Data subject rights implementation
   - Cookie consent implementation
2. Security compliance:
   - Data encryption (at rest and in transit)
   - Authentication security
   - Input sanitization
   - OWASP Top 10 check
3. Regulatory compliance:
   - GDPR requirements (if applicable)
   - CCPA requirements (if applicable)
   - Industry-specific requirements
4. Accessibility compliance:
   - WCAG 2.1 AA verification
   - Screen reader compatibility
   - Keyboard navigation

Format: Compliance Certification Report
Timeline: 2 days
```

### ステップ2: 分析（3〜4日目、並行、ステップ1 の後）

#### 📊 テスト結果アナライザー — 品質メトリクスの集約
```
Activate Test Results Analyzer for quality metrics aggregation on [PROJECT].

Input: ALL Step 1 reports
Deliverables required:
1. Aggregate quality dashboard:
   - Overall quality score
   - Category breakdown (visual, functional, performance, security, compliance)
   - Issue severity distribution
   - Trend analysis (if multiple test cycles)
2. Issue prioritization:
   - Critical issues (must fix before production)
   - High issues (should fix before production)
   - Medium issues (fix in next sprint)
   - Low issues (backlog)
3. Risk assessment:
   - Production readiness probability
   - Remaining risk areas
   - Recommended mitigations

Format: Quality Metrics Dashboard
Timeline: 1 day
```

#### 🔄 ワークフローオプティマイザー — プロセス効率レビュー
```
Activate Workflow Optimizer for process efficiency review on [PROJECT].

Input: Phase 3 execution data + Step 1 findings
Deliverables required:
1. Process efficiency analysis:
   - Dev↔QA loop efficiency (first-pass rate, average retries)
   - Bottleneck identification
   - Time-to-resolution for different issue types
2. Improvement recommendations:
   - Process changes for Phase 6 operations
   - Automation opportunities
   - Quality improvement suggestions

Format: Optimization Recommendations Report
Timeline: 1 day
```

#### 🏗️ インフラメンテナー — 本番稼働準備チェック
```
Activate Infrastructure Maintainer for production readiness on [PROJECT].

Deliverables required:
1. Production environment validation:
   - All services healthy and responding
   - Auto-scaling configured and tested
   - Load balancer configuration verified
   - SSL/TLS certificates valid
2. Monitoring validation:
   - All critical metrics being collected
   - Alert rules configured and tested
   - Dashboard access verified
   - Log aggregation working
3. Disaster recovery validation:
   - Backup systems operational
   - Recovery procedures documented and tested
   - Failover mechanisms verified
4. Security validation:
   - Firewall rules reviewed
   - Access controls verified
   - Secrets management confirmed
   - Vulnerability scan clean

Format: Infrastructure Readiness Report
Timeline: 1 day
```

### ステップ3: 最終判定（5〜7日目、逐次）

#### 🔍 リアリティチェッカー — 最終判決
```
Activate Reality Checker for final integration testing on [PROJECT].

MANDATORY PROCESS — DO NOT SKIP:

Step 1: Reality Check Commands
- Verify what was actually built (ls, grep for claimed features)
- Cross-check claimed features against specification
- Run comprehensive screenshot capture
- Review all evidence from Step 1 and Step 2

Step 2: QA Cross-Validation
- Review Evidence Collector findings
- Cross-reference with API Tester results
- Verify Performance Benchmarker data
- Confirm Legal Compliance Checker findings

Step 3: End-to-End System Validation
- Test COMPLETE user journeys (not individual features)
- Verify responsive behavior across ALL devices
- Check interaction flows end-to-end
- Review actual performance data

Step 4: Specification Reality Check
- Quote EXACT text from original specification
- Compare with ACTUAL implementation evidence
- Document EVERY gap between spec and reality
- No assumptions — evidence only

VERDICT OPTIONS:
- READY: Overwhelming evidence of production readiness (rare first pass)
- NEEDS WORK: Specific issues identified with fix list (expected)
- NOT READY: Major architectural issues requiring Phase 1/2 revisit

Format: Reality-Based Integration Report
Default: NEEDS WORK unless proven otherwise
```

## 品質ゲート — 最終ゲート

| # | 基準 | しきい値 | 必要なエビデンス |
|---|-----------|-----------|-------------------|
| 1 | ユーザージャーニーの完了 | すべてのクリティカルパスがエンドツーエンドで動作 | リアリティチェッカーのスクリーンショット |
| 2 | デバイス間の一貫性 | デスクトップ + タブレット + モバイルがすべて動作 | レスポンシブスクリーンショット |
| 3 | パフォーマンス認定 | P95 < 200ms、LCP < 2.5s、稼働率 > 99.9% | パフォーマンスベンチマーカーレポート |
| 4 | セキュリティの検証 | クリティカル脆弱性ゼロ | セキュリティスキャン + コンプライアンスレポート |
| 5 | コンプライアンス認定 | すべての規制要件を満たしている | 法的コンプライアンスチェッカーレポート |
| 6 | 仕様への準拠 | 仕様要件の100%が実装済み | 項目ごとの検証 |
| 7 | インフラの準備完了 | 本番環境が検証済み | インフラメンテナーレポート |

## ゲート判定

**唯一の権限者**: リアリティチェッカー

### 合格（フェーズ5 へ移行）の場合:
```markdown
## フェーズ4 → フェーズ5 引き継ぎパッケージ

### ローンチチーム向け:
- リアリティチェッカーの認定レポート
- パフォーマンス認定
- コンプライアンス認定
- インフラ準備完了レポート
- 既知の制限事項（ある場合）

### グロースハッカー向け:
- ユーザーへの提供準備が整った製品
- マーケティングメッセージ用の機能リスト
- 信頼性のためのパフォーマンスデータ

### DevOps オートメーター向け:
- 本番デプロイの承認
- ブルーグリーンデプロイメント計画
- ロールバック手順の確認
```

### 要修正（フェーズ3 へ差し戻し）の場合:
```markdown
## フェーズ4 → フェーズ3 差し戻しパッケージ

### 修正リスト（リアリティチェッカーより）:
1. [クリティカル問題1]: [説明 + エビデンス + 修正指示]
2. [クリティカル問題2]: [説明 + エビデンス + 修正指示]
3. [高優先度問題1]: [説明 + エビデンス + 修正指示]
...

### プロセス:
- 問題は Dev↔QA ループへ（フェーズ3 のメカニズム）
- 各修正はエビデンスコレクターの QA を通過する必要あり
- すべての修正完了後 → フェーズ4 ステップ3 へ戻る
- リアリティチェッカーが更新されたエビデンスで再評価

### 想定: 2〜3回の修正サイクルは正常
```

### 準備未完了（フェーズ1/2 へ差し戻し）の場合:
```markdown
## フェーズ4 → フェーズ1/2 差し戻しパッケージ

### 特定されたアーキテクチャ上の問題:
1. [根本的な問題]: [フェーズ3 で修正できない理由]
2. [構造的な問題]: [アーキテクチャレベルで変更が必要なこと]

### 推奨アクション:
- [ ] システムアーキテクチャの改訂（フェーズ1）
- [ ] 基盤の再構築（フェーズ2）
- [ ] スコープ削減と再定義（フェーズ1）

### スタジオプロデューサーの判断が必要
```

---

*フェーズ4 は、リアリティチェッカーが圧倒的なエビデンスとともに「合格」判定を出した時点で完了となります。「要修正」は初回の予想される結果であり、システムは動作しているが磨きが必要であることを意味します。*
