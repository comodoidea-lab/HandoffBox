# Implementation Workflow

[English](./implementation-flow.md) | 日本語

このワークフローは、実装担当AIのための標準作業手順です。実装重視の
ワークフローを参考にしていますが、特定モデルの内部推論を再現するものでは
ありません。

AIエージェントに機能実装、バグ修正、プロトタイプ作成、UI挙動変更を依頼する
ときに使います。

## HandoffBox Relay内での位置づけ

| 層 | 役割 |
|----|------|
| HandoffBox Issue | 事実、判断、根拠、承認状態の正本 |
| HandoffBox Relay | Hermes、agmsg、作業エージェントの連携モデル |
| Implementation Workflow | 実装担当AIの標準作業手順 |

このワークフロー自体は証拠ではありません。証拠は commit、PR、test output、
log、screenshot、deployment、Issue comment などとして記録します。

## 実装前

ファイルを編集する前に行います。

1. ローカル文脈を読む。
   - 関連するソースファイル
   - README / AGENTS / プロジェクト文書
   - package、build、test、framework設定
   - 既存の命名、レイアウト、スタイル規約

2. タスクを整理する。
   - 目的
   - やらないこと
   - 前提
   - 制約
   - 影響するファイルやコンポーネント
   - 承認境界

3. エッジケースを洗い出す。
   - 空状態
   - エラー状態
   - 狭い画面や小さいviewport
   - データ欠落
   - 重複操作
   - 権限や認証の失敗

4. 検証経路を決める。
   - build command
   - test command
   - lint / typecheck command
   - browserまたはdevice確認
   - UI変更がある場合のscreenshotや目視確認

## 実装中

変更は小さく、局所的にします。

- 新しいパターンより、リポジトリの既存規約を優先する。
- 設定変更は必要な場合だけ先に行う。
- 仕上げより先に土台を実装する。
- 名前は明確にする。
- タスクに不要な大規模リファクタは避ける。
- 失敗を隠さない。有用なエラー出力は残す。
- データ、認証、課金、デプロイ、破壊的操作、既存Issueの承認状態に触れる場合は、
  停止して人間の承認を求める。

## 実装後

成功報告の前に検証します。

1. 関連チェックを実行する。
   - tests
   - build
   - lint
   - typecheck
   - preview または local app run

2. 挙動を確認する。
   - ユーザーフローを再生する
   - 実装前に挙げたエッジケースを確認する
   - UI変更がある場合は実画面を見る
   - 期待値と実際の出力を比較する

3. 短いフィードバックループで修正する。
   - 失敗している手順を特定する
   - 正確なAPIまたは近くのコードを確認する
   - 最小の局所修正を優先する
   - 失敗したチェックを再実行する

4. 証拠を記録する。
   - 変更したファイル
   - 実行したコマンド
   - 通過したチェック
   - スキップしたチェックと理由
   - 必要に応じたscreenshotやlog
   - 残リスク

## Handoff Fields

実装作業後にハンドオフを残す場合は、次の項目を含めます。

```md
## Implementation Plan
- Goal:
- Assumptions:
- Constraints:
- Edge cases:
- Verification path:

## Implementation Result
- Changed:
- Verified:
- Failed checks:
- Skipped checks:
- Residual risk:
- Evidence:
```

## Agent Prompt

```text
HandoffBox Implementation Workflow を使ってください。

編集前にローカル文脈を読み、目的、前提、制約、エッジケース、検証経路を明示してください。

最小の有用な変更を実装してください。リポジトリの既存規約に従ってください。

編集後は関連チェックを実行し、挙動を確認し、証拠を記録し、スキップしたチェックや
残リスクがあれば明記してください。

人間の明示的な承認なしに、既存のHandoffBox Issueの更新、クローズ、承認状態変更を
行わないでください。
```
