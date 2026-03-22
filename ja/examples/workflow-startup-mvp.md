# マルチエージェントワークフロー：スタートアップ MVP

> アイデアから出荷済み MVP まで、複数のエージェントをどのように連携させるかのステップバイステップの例。

## シナリオ

SaaS MVP を構築しています ── リモートチーム向けのチームレトロスペクティブツールです。ユーザー登録、コア機能、ランディングページを備えた動作する製品を4週間で出荷する必要があります。

## エージェントチーム

| エージェント | このワークフローでの役割 |
|-------|---------------------|
| Sprint Prioritizer | プロジェクトを週次スプリントに分割する |
| UX Researcher | 簡易ユーザーインタビューでアイデアを検証する |
| Backend Architect | API とデータモデルを設計する |
| Frontend Developer | React アプリを構築する |
| Rapid Prototyper | 最初のバージョンを素早く動かす |
| Growth Hacker | 構築しながらローンチ戦略を立案する |
| Reality Checker | 各マイルストーンの品質を確認してから次に進む |

## ワークフロー

### 第1週：調査 + アーキテクチャ

**ステップ 1 — Sprint Prioritizer を起動**

```
Activate Sprint Prioritizer.

Project: RetroBoard — a real-time team retrospective tool for remote teams.
Timeline: 4 weeks to MVP launch.
Core features: user auth, create retro boards, add cards, vote, action items.
Constraints: solo developer, React + Node.js stack, deploy to Vercel + Railway.

Break this into 4 weekly sprints with clear deliverables and acceptance criteria.
```

**ステップ 2 — UX Researcher を起動（並行）**

```
Activate UX Researcher.

I'm building a team retrospective tool for remote teams (5-20 people).
Competitors: EasyRetro, Retrium, Parabol.

Run a quick competitive analysis and identify:
1. What features are table stakes
2. Where competitors fall short
3. One differentiator we could own

Output a 1-page research brief.
```

**ステップ 3 — Backend Architect に引き継ぐ**

```
Activate Backend Architect.

Here's our sprint plan: [paste Sprint Prioritizer output]
Here's our research brief: [paste UX Researcher output]

Design the API and database schema for RetroBoard.
Stack: Node.js, Express, PostgreSQL, Socket.io for real-time.

Deliver:
1. Database schema (SQL)
2. REST API endpoints list
3. WebSocket events for real-time board updates
4. Auth strategy recommendation
```

### 第2週：コア機能の構築

**ステップ 4 — Frontend Developer + Rapid Prototyper を起動**

```
Activate Frontend Developer.

Here's the API spec: [paste Backend Architect output]

Build the RetroBoard React app:
- Stack: React, TypeScript, Tailwind, Socket.io-client
- Pages: Login, Dashboard, Board view
- Components: RetroCard, VoteButton, ActionItem, BoardColumn

Start with the Board view — it's the core experience.
Focus on real-time: when one user adds a card, everyone sees it.
```

**ステップ 5 — 中間地点でリアリティチェック**

```
Activate Reality Checker.

We're at week 2 of a 4-week MVP build for RetroBoard.

Here's what we have so far:
- Database schema: [paste]
- API endpoints: [paste]
- Frontend components: [paste]

Evaluate:
1. Can we realistically ship in 2 more weeks?
2. What should we cut to make the deadline?
3. Any technical debt that will bite us at launch?
```

### 第3週：磨き上げ + ランディングページ

**ステップ 6 — Frontend Developer が続行し、Growth Hacker が開始**

```
Activate Growth Hacker.

Product: RetroBoard — team retrospective tool, launching in 1 week.
Target: Engineering managers and scrum masters at remote-first companies.
Budget: $0 (organic launch only).

Create a launch plan:
1. Landing page copy (hero, features, CTA)
2. Launch channels (Product Hunt, Reddit, Hacker News, Twitter)
3. Day-by-day launch sequence
4. Metrics to track in week 1
```

### 第4週：ローンチ

**ステップ 7 — 最終リアリティチェック**

```
Activate Reality Checker.

RetroBoard is ready to launch. Evaluate production readiness:

- Live URL: [url]
- Test accounts created: yes
- Error monitoring: Sentry configured
- Database backups: daily automated

Run through the launch checklist and give a GO / NO-GO decision.
Require evidence for each criterion.
```

## 主要なパターン

1. **順次引き継ぎ**：各エージェントの出力が次のエージェントの入力になる
2. **並行作業**：第1週では UX Researcher と Sprint Prioritizer を同時に実行できる
3. **品質ゲート**：中間地点とローンチ前の Reality Checker が壊れたコードの出荷を防ぐ
4. **コンテキストの引き渡し**：常に前のエージェントの出力を次のプロンプトに貼り付ける ── エージェントはメモリを共有しない

## ヒント

- エージェント間でアウトプットをコピーペーストする ── 要約せず、完全な出力を使う
- Reality Checker が問題を指摘した場合は、関係するスペシャリストに修正を依頼する
- このフローに慣れたら、手動バージョンを自動化するために Orchestrator エージェントの活用も検討する
