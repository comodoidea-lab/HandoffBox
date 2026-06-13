# HandoffBox

> Yesterday's self hands today's self the next step.  
> 昨日の自分から今日の自分へ、次のステップを引き継ぐ。

HandoffBox is not another productivity app.  
It is a simple operating principle for reducing the **restart tax** of unfinished work.

HandoffBoxは、単なる生産性向上アプリではありません。  
未完了の作業による「再開コスト」を削減するための、シンプルな運用原則です。

**Repository / リポジトリ**

- https://github.com/comodoidea-lab/HandoffBox
- `git@github.com:comodoidea-lab/HandoffBox.git`

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

### Handoff template / 引き継ぎテンプレート（1 Issue にまとめる）

人間向けと AI 向けの情報を **1つの Issue** に書く。  
上段は明日の自分向け（平易）、下段は AI エージェント向け（技術詳細）。

```md
# Handoff: {プロジェクト名}

## 止めた場所
（明日の自分向け。平易に）

## 止めた理由
（明日の自分向け。平易に）

## 次の1手（15分以内）
（明日の自分向け。最初にやることだけ）

---

## Context
- Repo:
- Branch / commit:
- Local path:
- Deploy / env:

## Stopped at
（具体的なファイル・機能・未完了タスク）

## Why stopped
（ブロッカー・判断・時間切れなど）

## Next step (≤15 min)
1. （実行コマンド付きの最初の1手）
2. ...

## Resume notes
（関連ファイル、既知の罠、前回の試行結果）
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

**One issue, two audiences.**  
**Issueは1つ。読み手は2人（明日の自分 + AI）。**

| Field | For whom | Purpose |
|-------|----------|---------|
| 止めた場所 / 理由 / 次の1手 | Human (you tomorrow) | 状況の把握と次の1手 |
| Context / Stopped at / Resume notes | AI agent | 再開に必要な技術コンテキスト |

タイトル: `Handoff: {project} — {summary}`

---

## Agent prompt / エージェント向けプロンプト

初めて使う AI エディター向け。セッション終了時に **HandoffBox に Issue を1つ** 作成する。

```
HandoffBox の README を読んで、今の作業セッションの Handoff を GitHub Issue として記録してください。

HandoffBox リポジトリ:
- https://github.com/comodoidea-lab/HandoffBox
- git@github.com:comodoidea-lab/HandoffBox.git

## 手順
1. 上記リポジトリの README.md を読む（初回は Web または clone で取得）
2. HandoffBox に Issue を1つだけ作成する

## Issue
- リポジトリ: comodoidea-lab/HandoffBox
- タイトル: `Handoff: {プロジェクト名} — {一言サマリー}`
- 本文: README の「引き継ぎテンプレート」に従う（人間向け + AI向けを1つにまとめる）
- 文体: 上段（止めた場所〜次の1手）は日本語・平易に。下段（Context〜Resume notes）はコマンド・パス・ブランチを正確に
- 必須セクション: 止めた場所 / 止めた理由 / 次の1手（15分以内）/ Context / Stopped at / Why stopped / Next step / Resume notes

## ルール
- Issue は1つだけ。人間用と AI用に分割しない
- 推測で埋めない。不明な点は「不明」と書く
- 完了済みの作業も簡潔に列挙する
- Issue 作成後、URL を返す
```

### One-liner / 一言プロンプト

```
HandoffBox（ https://github.com/comodoidea-lab/HandoffBox ）の README を読んで、Handoff Issue を1つ作成して。
```

### gh CLI example / 作成例

```bash
gh issue create -R comodoidea-lab/HandoffBox \
  --title "Handoff: my-project — short summary" \
  --body "$(cat <<'EOF'
# Handoff: my-project

## 止めた場所

## 止めた理由

## 次の1手（15分以内）

---

## Context
- Repo:
- Branch / commit:
- Local path:
- Deploy / env:

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
