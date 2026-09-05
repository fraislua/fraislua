---
name: daily-thinking
description: 日々の思考ログ（Daily Thinking）の記録、壁打ち、関心テーマの深掘り、および評価の蓄積を行う。Morning Briefで提示された問いへの回答受け取りや、ユーザーの思考・アイデア・考察の整理、過去ログの検索、Google Drive（/GeminiSpark/02_Silver_Structured/Daily_Thinking/）への保存に使用する。
allowed-tools: drive context_service_agent google
---

# Daily Thinking スキル

## 概要
ユーザーの日々の思考、Morning Briefの問いに対する回答、アイデア、技術的な考察、およびトピックに対する評価（関心度・有用性）を受け取り、深掘り・壁打ちを行った上でGoogle Driveに思考ログとして蓄積・構造化します。

## トリガー条件
- Morning Briefで提示された「Daily Thinking」の問いに対する回答が送信されたとき
- ユーザーから「今日の思考ログを保存して」「これについて考えたことをまとめたい」「過去のDaily Thinkingを振り返りたい」と指示されたとき

## 実行手順

### 1. 入力の受け取りと意図の把握
- ユーザーの回答・考察・アイデア・評価内容を受け取る。
- 該当する思考日（基準日）を特定する（デフォルトは本日 `YYYY-MM-DD`）。

### 2. 思考の深掘りと壁打ち（構造化）
- ユーザーの考察に対し、以下の観点から有益なフィードバックや発展的な視点を提示する:
  - **ゲーム開発・企画**: ゲームシステム、UI/UX、プレイヤー心理、実装工数、技術選定（Unity / C# 等）
  - **就活・キャリア**: 面接やポートフォリオで語れるストーリー、自己分析、業界トレンド
  - **技術・インフラ**: サーバー運用、自動化、効率的なワークフロー
- 単に肯定するだけでなく、論点の整理、課題の深掘り、次のアクションへの繋がりを提示する。

### 3. 評価（フィードバック）の整理
- 提示したトピックに対するユーザーの評価（興味あり/なし、有用/不要など）を記録・分類する。
- ユーザーの好みを蓄積し、今後のMorning Briefや提案のパーソナライズ精度を高める情報として整理する。

### 4. Google Driveへの思考ログ保存・更新
- 保存先パス: `/GeminiSpark/02_Silver_Structured/Daily_Thinking/Daily_Thinking_YYYYMMDD.md`
  - ※日付は思考を行った日（通常は当日）。
- フォルダ `/GeminiSpark/02_Silver_Structured/Daily_Thinking/` を `drive:search_files` で特定し、ファイルを配置・保存する。
- 同日のファイルが既に存在する場合は、内容を統合・追記して更新する。

【保存フォーマット (`Daily_Thinking_YYYYMMDD.md`)】
```markdown
# 🧠 Daily Thinking（YYYY年MM月DD日）

## 💭 本日の考察・思考ログ
### テーマ / 問い: [テーマ名]
- **ユーザーの考察**: 
  - [ユーザーが考えたこと、意見、アイデア]
- **深掘り・分析・壁打ちメモ**:
  - [整理された要点、発展的な視点、関連する技術・企画アプローチ]
- **評価 / 関心度**: [高 / 中 / 低 / スキップ]

## 🎯 次のアクション・今後の検討事項
- [ ] 今後試したいことや深掘りしたいタスク

## 📝 過去ログ・関連トピックとの接続
- [過去の関連思考ログやプロジェクトとの紐付きメモ]
```

### 5. 過去の思考ログの検索・振り返り
- ユーザーから「先週のDaily Thinkingで何を話したっけ？」「〇〇についての以前の考察を教えて」と尋ねられた際は、`drive:search_files` や `context_service_agent:get_context` を用いて `/GeminiSpark/02_Silver_Structured/Daily_Thinking/` 内のファイルを検索し、回答する。
