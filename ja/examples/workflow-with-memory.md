# マルチエージェントワークフロー：永続メモリを使ったスタートアップ MVP

> [workflow-startup-mvp.md](workflow-startup-mvp.md) と同じスタートアップ MVP ワークフローですが、MCP メモリサーバーがエージェント間の状態を管理します。コピーペーストによる引き継ぎはもう不要です。

## 手動引き継ぎの問題点

標準ワークフローでは、エージェント間の移行はすべてこのような形になります：

```
Activate Backend Architect.

Here's our sprint plan: [paste Sprint Prioritizer output]
Here's our research brief: [paste UX Researcher output]

Design the API and database schema for RetroBoard.
...
```

あなたが接着剤の役割を担います。エージェント間でアウトプットをコピーペーストし、完了した内容を追跡し、コンテキストが失われないように注意します。小規模プロジェクトでは機能しますが、以下の状況では破綻します：

- セッションがタイムアウトし、アウトプットが失われる
- 複数のエージェントが同じコンテキストを必要とする
- QA が失敗し、以前の状態に戻す必要がある
- プロジェクトが複数のセッションにわたって数日または数週間続く

## 解決策

MCP メモリサーバーがインストールされていると、エージェントは成果物をメモリに保存し、必要なものを自動的に取得します。引き継ぎはこのようになります：

```
Activate Backend Architect.

Project: RetroBoard. Recall previous context for this project
and design the API and database schema.
```

エージェントはメモリで RetroBoard のコンテキストを検索し、前のエージェントが保存したスプリント計画と調査概要を見つけ、そこから作業を再開します。

## セットアップ

`remember`、`recall`、`rollback` 操作をサポートする MCP 互換のメモリサーバーをインストールします。セットアップについては [integrations/mcp-memory/README.md](../integrations/mcp-memory/README.md) を参照してください。

## シナリオ

標準ワークフローと同じ内容：SaaS チームレトロスペクティブツール（RetroBoard）、MVP まで4週間、ソロ開発者。

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

各エージェントはプロンプトにメモリインテグレーションのセクションを持っています（追加方法は [integrations/mcp-memory/README.md](../integrations/mcp-memory/README.md) を参照してください）。

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
Remember your sprint plan tagged for this project when done.
```

Sprint Prioritizer はスプリント計画を作成し、`sprint-prioritizer`、`retroboard`、`sprint-plan` のタグを付けてメモリに保存します。

**ステップ 2 — UX Researcher を起動（並行）**

```
Activate UX Researcher.

I'm building a team retrospective tool for remote teams (5-20 people).
Competitors: EasyRetro, Retrium, Parabol.

Run a quick competitive analysis and identify:
1. What features are table stakes
2. Where competitors fall short
3. One differentiator we could own

Output a 1-page research brief. Remember it tagged for this project when done.
```

UX Researcher は調査概要を `ux-researcher`、`retroboard`、`research-brief` のタグを付けてメモリに保存します。

**ステップ 3 — Backend Architect に引き継ぐ**

```
Activate Backend Architect.

Project: RetroBoard. Recall the sprint plan and research brief from previous agents.
Stack: Node.js, Express, PostgreSQL, Socket.io for real-time.

Design:
1. Database schema (SQL)
2. REST API endpoints list
3. WebSocket events for real-time board updates
4. Auth strategy recommendation

Remember each deliverable tagged for this project and for the frontend-developer.
```

Backend Architect はメモリからスプリント計画と調査概要を自動的に取得します。コピーペースト不要です。スキーマと API 仕様を `backend-architect`、`retroboard`、`api-spec`、`frontend-developer` のタグを付けてメモリに保存します。

### 第2週：コア機能の構築

**ステップ 4 — Frontend Developer + Rapid Prototyper を起動**

```
Activate Frontend Developer.

Project: RetroBoard. Recall the API spec and schema from the Backend Architect.

Build the RetroBoard React app:
- Stack: React, TypeScript, Tailwind, Socket.io-client
- Pages: Login, Dashboard, Board view
- Components: RetroCard, VoteButton, ActionItem, BoardColumn

Start with the Board view — it's the core experience.
Focus on real-time: when one user adds a card, everyone sees it.
Remember your progress tagged for this project.
```

Frontend Developer はメモリから API 仕様を取得してそれに沿って構築します。

**ステップ 5 — 中間地点でリアリティチェック**

```
Activate Reality Checker.

Project: RetroBoard. We're at week 2 of a 4-week MVP build.

Recall all deliverables from previous agents for this project.

Evaluate:
1. Can we realistically ship in 2 more weeks?
2. What should we cut to make the deadline?
3. Any technical debt that will bite us at launch?

Remember your verdict tagged for this project.
```

Reality Checker は、スプリント計画、調査概要、スキーマ、API 仕様、フロントエンドの進捗など、これまでに作成されたすべてのものを完全に把握できます ── あなたがそれらを収集してペーストする必要はありません。

### 第3週：磨き上げ + ランディングページ

**ステップ 6 — Frontend Developer が続行し、Growth Hacker が開始**

```
Activate Growth Hacker.

Product: RetroBoard — team retrospective tool, launching in 1 week.
Target: Engineering managers and scrum masters at remote-first companies.
Budget: $0 (organic launch only).

Recall the project context and Reality Checker's verdict.

Create a launch plan:
1. Landing page copy (hero, features, CTA)
2. Launch channels (Product Hunt, Reddit, Hacker News, Twitter)
3. Day-by-day launch sequence
4. Metrics to track in week 1

Remember the launch plan tagged for this project.
```

### 第4週：ローンチ

**ステップ 7 — 最終リアリティチェック**

```
Activate Reality Checker.

Project: RetroBoard, ready to launch.

Recall all project context, previous verdicts, and the launch plan.

Evaluate production readiness:
- Live URL: [url]
- Test accounts created: yes
- Error monitoring: Sentry configured
- Database backups: daily automated

Run through the launch checklist and give a GO / NO-GO decision.
Require evidence for each criterion.
```

### QA が失敗した場合：ロールバック

標準ワークフローでは、Reality Checker が成果物を却下した場合、担当エージェントに戻り、何が問題だったかを説明しなければなりません。メモリがあれば、リカバリのループがより緊密になります：

```
Activate Backend Architect.

Project: RetroBoard. The Reality Checker flagged issues with the API design.
Recall the Reality Checker's feedback and your previous API spec.
Roll back to your last known-good schema and address the specific issues raised.
Remember the updated deliverables when done.
```

Backend Architect は Reality Checker が指摘した問題を確認し、自身の以前の作業を取得し、チェックポイントにロールバックして修正を行うことができます ── あなたが手動でバージョンを追跡する必要はありません。

## 比較：ビフォー/アフター

| 観点 | 標準ワークフロー | メモリあり |
|--------|------------------|-------------|
| **引き継ぎ** | エージェント間で完全な出力をコピーペースト | エージェントが必要なものを自動取得 |
| **コンテキスト喪失** | セッションタイムアウトですべてが消える | メモリはセッションをまたいで永続 |
| **複数エージェントのコンテキスト** | N 個のエージェントからコンテキストを手動でまとめる | エージェントがプロジェクトタグでメモリを検索 |
| **QA 失敗時の回復** | 何が問題だったかを手動で説明する | エージェントがフィードバックを取得してロールバック |
| **複数日にわたるプロジェクト** | セッションごとにコンテキストを再構築する | エージェントが中断したところから再開 |
| **必要なセットアップ** | なし | MCP メモリサーバーのインストール |

## 主要なパターン

1. **すべてにプロジェクト名のタグを付ける**：これが取得を機能させる鍵です。すべてのメモリに `retroboard`（またはあなたのプロジェクト名）のタグを付けます。
2. **受け取るエージェント向けに成果物にタグを付ける**：Backend Architect が API 仕様を完成したら、Frontend Developer がそれを取得できるよう `frontend-developer` のタグをメモリに付けます。
3. **Reality Checker が完全な可視性を持つ**：すべてのエージェントが作業をメモリに保存するため、Reality Checker はあなたがまとめなくてもプロジェクトのすべてを取得できます。
4. **ロールバックで手動のやり直しを代替する**：何かが失敗した場合、何が変わったかを調べようとする代わりに、最後のチェックポイントにロールバックします。

## ヒント

- すべてのエージェントを一度に変更する必要はありません。最もよく使うエージェントにメモリインテグレーションを追加することから始め、徐々に拡張します。
- メモリの指示はコードではなくプロンプトです。LLM がそれを解釈し、必要に応じて MCP ツールを呼び出します。スタイルに合わせて文言を調整できます。
- `remember`、`recall`、`rollback`、`search` ツールをサポートする任意の MCP 互換メモリサーバーがこのワークフローで動作します。
