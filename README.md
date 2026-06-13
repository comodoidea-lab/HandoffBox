# HandoffBox

> Yesterday's self hands today's self the next step.  
> 昨日の自分から今日の自分へ、次のステップを引き継ぐ。

HandoffBox is not another productivity app.  
It is a simple operating principle for reducing the **restart tax** of unfinished work.

HandoffBoxは、単なる生産性向上アプリではありません。  
未完了の作業による「再開コスト」を削減するための、シンプルな運用原則です。

---

## The Problem / 問題点

As solo builders, we often stop at 80%.

Not because of a lack of skill or time, but because every restart requires reconstructing context:

- Where did I stop?
- Why did I stop?
- What should I do next?

一人で作業する人は、しばしば80%のところで中断します。  
スキルや時間の不足ではなく、再開のたびに状況を再構築する必要があるからです。

- どこで止めたか？
- なぜ止めたか？
- 次に何をすべきか？

The cost of remembering becomes the reason projects never finish.  
思い出すコストが、プロジェクトを終わらせない原因になります。

---

## The Solution / 解決策

Before stopping work, leave a handoff.  
作業を止める前に、引き継ぎを残す。

Tomorrow, execute the next step. When finished, close the loop.  
明日は次のステップを実行するだけ。完了したらループを閉じる。

### Human handoff template / 人間用テンプレート

```md
## 止めた場所

## 止めた理由

## 次の1手（15分以内）
```

### AI handoff template / AI用テンプレート

```md
## Context
- Repo:
- Branch / commit:
- Local path:
- Deploy / env:

## Stopped at
(具体的なファイル・機能・未完了タスク)

## Why stopped
(ブロッカー・判断・時間切れなど)

## Next step (≤15 min)
1. (実行コマンド付きの最初の1手)
2. ...

## Resume notes
(関連ファイル、既知の罠、前回の試行結果)
```

---

## Why GitHub Issues? / なぜ GitHub Issues？

HandoffBox was originally imagined as a dedicated application.  
HandoffBoxは当初、専用アプリとして構想されました。

Then we realized GitHub Issues already had everything we needed:

- Open / Comment / Pin / Notifications / Close

GitHub Issues には、すでに必要な機能が揃っていました。

- オープン / コメント / ピン留め / 通知 / クローズ

The missing piece wasn't another tool. It was the habit of leaving a handoff.  
欠けていたのは別のツールではなく、**ハンドオフを残す習慣**でした。

---

## Philosophy / 理念

Build less. Finish more.  
構築は少なく。完了を多く。

Reduce restart tax. Close loops.  
再開コストを減らす。ループを閉じる。

Yesterday's self should help today's self.  
昨日の自分が、今日の自分を助ける。

---

## Workflow / ワークフロー

```
Issue → Work → Leave handoff → Resume → Close
課題 → 作業 → ハンドオフを残す → 再開 → クローズ
```

**Two issues, two audiences.**  
**Issueは2つ。読み手も2つ。**

| Issue | For whom | Purpose |
|-------|----------|---------|
| `Handoff: {project} — {summary}` | Human (you tomorrow) | 状況の把握と次の1手 |
| `AI Handoff: {project} — {summary}` | AI agent | 再開に必要な技術コンテキスト |

---

## Agent prompt / エージェント向けプロンプト

セッション終了時に、この README を読んだうえで **HandoffBox に Issue を2つ** 作成してください。  
順番は必ず **人間用 → AI用** です。

```
このリポジトリ（comodoidea-lab/HandoffBox）の README.md を読んでから、
今の作業セッションの Handoff を GitHub Issue として記録してください。

## 手順
1. まず人間用 Issue を1つ作成する
2. 続けて AI用 Issue を1つ作成する

## 人間用 Issue
- タイトル: `Handoff: {プロジェクト名} — {一言サマリー}`
- 本文: README の「人間用テンプレート」に従う
- 文体: 日本語、平易に。技術詳細は最小限
- 必須: 止めた場所 / 止めた理由 / 次の1手（15分以内）

## AI用 Issue
- タイトル: `AI Handoff: {プロジェクト名} — {一言サマリー}`
- 本文: README の「AI用テンプレート」に従う
- 文体: 日本語ベースでよいが、コマンド・パス・ブランチは正確に
- 必須: Context / Stopped at / Why stopped / Next step / Resume notes
- 次の1手には実行コマンドを含める

## ルール
- 推測で埋めない。不明な点は「不明」と書く
- 完了済みの作業も簡潔に列挙する
- Issue 作成後、両方の URL を返す
```

### One-liner / 一言プロンプト

```
HandoffBox の README を読んで、人間用と AI用の Handoff Issue をこのリポジトリに順番に作成して。
```

### gh CLI example / 作成例

```bash
# 1. Human handoff
gh issue create -R comodoidea-lab/HandoffBox \
  --title "Handoff: my-project — short summary" \
  --body "$(cat <<'EOF'
## 止めた場所

## 止めた理由

## 次の1手（15分以内）
EOF
)"

# 2. AI handoff
gh issue create -R comodoidea-lab/HandoffBox \
  --title "AI Handoff: my-project — short summary" \
  --body "$(cat <<'EOF'
## Context
- Repo:
- Branch / commit:
- Local path:

## Stopped at

## Why stopped

## Next step (≤15 min)
1.

## Resume notes
EOF
)"
```

---

That's it.  
以上です。
