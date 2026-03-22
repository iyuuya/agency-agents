# マルチエージェントワークフロー：ランディングページスプリント

> 4つのエージェントを使い、1日でコンバージョン最適化されたランディングページを公開する。

## シナリオ

新製品のローンチに向けたランディングページが必要です。見た目が良く、訪問者をコンバートし、当日中に公開される必要があります。

## エージェントチーム

| エージェント | このワークフローでの役割 |
|-------|---------------------|
| Content Creator | コピーを書く |
| UI Designer | レイアウトとコンポーネント仕様を設計する |
| Frontend Developer | 構築する |
| Growth Hacker | コンバージョン向けに最適化する |

## ワークフロー

### 午前：コピー + デザイン（並行作業）

**ステップ 1a — Content Creator を起動**

```
Activate Content Creator.

Write landing page copy for "FlowSync" — an API integration platform
that connects any two SaaS tools in under 5 minutes.

Target audience: developers and technical PMs at mid-size companies.
Tone: confident, concise, slightly playful.

Sections needed:
1. Hero (headline + subheadline + CTA)
2. Problem statement (3 pain points)
3. How it works (3 steps)
4. Social proof (placeholder testimonial format)
5. Pricing (3 tiers: Free, Pro, Enterprise)
6. Final CTA

Keep it scannable. No fluff.
```

**ステップ 1b — UI Designer を起動（並行）**

```
Activate UI Designer.

Design specs for a SaaS landing page. Product: FlowSync (API integration platform).
Style: clean, modern, dark mode option. Think Linear or Vercel aesthetic.

Deliver:
1. Layout wireframe (section order + spacing)
2. Color palette (primary, secondary, accent, background)
3. Typography (font pairing, heading sizes, body size)
4. Component specs: hero section, feature cards, pricing table, CTA buttons
5. Responsive breakpoints (mobile, tablet, desktop)
```

### 昼：構築

**ステップ 2 — Frontend Developer を起動**

```
Activate Frontend Developer.

Build a landing page from these specs:

Copy: [paste Content Creator output]
Design: [paste UI Designer output]

Stack: HTML, Tailwind CSS, minimal vanilla JS (no framework needed).
Requirements:
- Responsive (mobile-first)
- Fast (no heavy assets, system fonts OK)
- Accessible (proper headings, alt text, focus states)
- Include a working email signup form (action URL: /api/subscribe)

Deliver a single index.html file ready to deploy.
```

### 午後：最適化

**ステップ 3 — Growth Hacker を起動**

```
Activate Growth Hacker.

Review this landing page for conversion optimization:

[paste the HTML or describe the current page]

Evaluate:
1. Is the CTA above the fold?
2. Is the value proposition clear in under 5 seconds?
3. Any friction in the signup flow?
4. What A/B tests would you run first?
5. SEO basics: meta tags, OG tags, structured data

Give me specific changes, not general advice.
```

## タイムライン

| 時間 | 作業 | エージェント |
|------|----------|-------|
| 9:00 | コピー + デザイン開始（並行） | Content Creator + UI Designer |
| 11:00 | 構築開始 | Frontend Developer |
| 14:00 | 初版完成 | — |
| 14:30 | コンバージョンレビュー | Growth Hacker |
| 15:30 | フィードバック反映 | Frontend Developer |
| 16:30 | 公開 | Vercel/Netlify にデプロイ |

## 主要なパターン

1. **並行キックオフ**：コピーとデザインは独立しているため同時進行
2. **マージポイント**：Frontend Developer は両方の出力が揃ってから開始する
3. **フィードバックループ**：Growth Hacker がレビューし、Frontend Developer が変更を反映する
4. **タイムボックス**：スコープクリープを防ぐため、各ステップに明確な時間制限がある
