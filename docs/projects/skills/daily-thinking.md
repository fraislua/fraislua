---
name: daily-thinking
description: 日々の思考ログ（Daily Thinking）の記録と壁打ちを行う。Daily Digest の「今日の問い」への回答、本人の考察・アイデア・意見を受け取り、論点を整理したうえで /KnowledgeBase/02_Knowledge/Daily_Thinking/ に保存する。過去の思考ログの振り返りにも使う。次の場合に保存する：問いへの回答が送られたとき、「思考ログを保存して」「これについて考えたことをまとめたい」「前に考えたことを振り返りたい」と言われたとき。
version: 2.1.0
changelog: CL-2026-11-04-08
---

# Daily Thinking

## ルール
- `/KnowledgeBase/` は Google Drive のマイドライブ直下のフォルダ。既存ファイルを書き換えない（AGENTS.md 5.1.0）。保存はすべて新規作成で、同じフォルダに同名ファイルがあれば名前の末尾に `-HHmm` を付ける。Google ドキュメント形式に変換されてもよい。
- **本人の考えと AI のコメントを必ず分けて書く。** 本人の考えの欄には、本人が言ったことだけを書く（意味を足さない・言い換えで強めない）。
- 壁打ちでは、単に肯定せず、論点の整理・前提の確認・反対の視点・次の一歩を示す。AI のコメントは提案であって本人の考えではない。
- 関心度・評価は本人が示した場合だけ記録する。

## 手順

### 1. 受け取りと壁打ち
- 本人の回答・考察を受け取る。日付は考えた日（通常は今日）。
- 必要に応じて、次の観点から問い返し・整理を行う。
  - ゲーム企画・開発（システム、UI/UX、プレイヤー心理、実装コスト、Unity/C#）
  - 就活・キャリア（面接やポートフォリオで語れる形、自己分析）
  - 技術・インフラ（自動化、ワークフロー）
- 会話のテンポを優先し、問い返しは1〜2個に絞る。

### 2. 保存
- 保存先: `/KnowledgeBase/02_Knowledge/Daily_Thinking/Daily_Thinking_YYYYMMDD.md`
- 同じ日のファイルが既にあれば書き換えず、`Daily_Thinking_YYYYMMDD-HHmm.md` として、今回の分だけを新しいファイルに書く。

```markdown
---
title: Daily_Thinking_YYYYMMDD
generated_by: gemini
sources: [chat YYYY-MM-DD]
status: verified
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
# 🧠 Daily Thinking（YYYY年MM月DD日）

## テーマ / 問い: …
### 本人の考え
- （本人の発言の要約。本人の言葉をできるだけ残す）
### AIの壁打ちメモ（提案・推測）
- …
### 関心度
- （本人が示した場合のみ：高 / 中 / 低）

## 次にやりたいこと（本人が言ったもの）
- [ ] …
```

- 本人が「やる」と言った次のアクションは、`open-items` スキルで申し送り台帳にも入れてよいか確認する。

### 3. 振り返り・検索
- 「前に〇〇について考えたこと」などと聞かれたら、`/KnowledgeBase/02_Knowledge/Daily_Thinking/` を検索し、該当ファイルのリンクを付けて答える。見つからなければ、検索した範囲を示して「見つかりませんでした」と答える。
