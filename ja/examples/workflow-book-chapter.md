# ワークフロー例：書籍の章の開発

> 粗削りな素材を戦略的な一人称の章の草稿に変換するための、明示的な改訂ループを持つシングルエージェントワークフロー。

## このワークフローを使う場面

著者が音声メモ、断片的なメモ、または戦略的なノートを持っているが、まだ整理された章の草稿がない場合に使用します。目的は汎用的なゴーストライティングではありません。目的は、カテゴリのポジショニングを強化し、著者の声を保持し、開かれた編集上の決断を明確に提示する章を生み出すことです。

## 使用するエージェント

| エージェント | 役割 |
|-------|------|
| Book Co-Author | 素材を版管理された章の草稿に変換し、編集メモと次のステップの質問を付ける |

## 起動例

```text
Activate Book Co-Author.

Book goal: Build authority around practical AI adoption for Mittelstand companies.
Target audience: Owners and operational leaders of 20-200 person businesses.
Chapter topic: Why most AI projects fail before implementation starts.
Desired draft maturity: First substantial draft.

Raw material:
- Voice memo: "The real failure happens in expectation setting, not tooling."
- Notes: Leaders buy software before defining the operational bottleneck.
- Story fragment: We nearly rolled out the wrong automation in a cabinetmaking workflow because the actual problem was quoting delays, not production throughput.
- Positioning angle: Practical realism over hype.

Produce:
1. Chapter objective and strategic role in the book
2. Any clarification questions you need
3. Chapter 2 - Version 1 - ready for review
4. Editorial notes on assumptions and proof gaps
5. Specific next-step revision requests
```

## 期待される出力の形式

Book Co-Author は5つのパートで回答するべきです：

1. `Target Outcome`（目標成果）
2. `Chapter Draft`（章の草稿）
3. `Editorial Notes`（編集メモ）
4. `Feedback Loop`（フィードバックループ）
5. `Next Step`（次のステップ）

## 品質基準

- 草稿は一人称の語り口を維持する
- 章には1つの明確な約束と内部的な論理がある
- 主張は素材に紐付けられているか、仮定として明示されている
- 汎用的な動機付けの言葉は排除されている
- 出力は曖昧な引き渡しではなく、明示的な改訂の質問で締めくくられる
