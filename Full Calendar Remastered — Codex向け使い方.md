# Full Calendar Remastered — Codex向け使い方

Full Calendar Remastered（FCR）は、Obsidian 上で予定を管理するためのプラグイン。

Codexからも予定の取得・追加・変更・削除ができる。

## 基本方針

Codexから操作するときは、次の順で方法を選ぶ。

1. **FCR の REST API**
    
    - 予定の取得・追加・変更・削除に推奨。
        
2. **Obsidian CLI + FCR API**
    
    - Obsidian内部の機能を直接使いたい場合。
        
3. **Markdown直接編集**
    
    - Full Note / Daily Note形式を単純に扱う場合のみ。
        

原則として、FCRが管理している予定はFCRのAPI経由で変更する。

---

## 1. REST APIから操作する

FCRのローカルAPIを有効にしている場合、Codexから `curl` やPythonで操作できる。

基本URL：

```text
http://127.0.0.1:8540/api/v1
```

認証にはFCRで発行したPATを使用する。

### 予定を取得

例：

```bash
curl \
  -H "Authorization: Bearer <PAT>" \
  http://127.0.0.1:8540/api/v1/events
```

### 予定を追加

例：

```bash
curl -X POST \
  -H "Authorization: Bearer <PAT>" \
  -H "Content-Type: application/json" \
  -d '{
    "calendarId": "personal-calendar",
    "event": {
      "title": "買い物",
      "date": "2026-09-10",
      "startTime": "15:00",
      "endTime": "16:00",
      "allDay": false
    }
  }' \
  http://127.0.0.1:8540/api/v1/events
```

実際の `calendarId` やイベント形式は、現在のFCR設定・API仕様を確認して使用すること。

---

## 2. Obsidian CLIから操作する

Obsidianが起動しており、CLIが利用可能なら、CodexからObsidianを操作できる。

### FCRのコマンドを探す

```bash
obsidian commands filter=full-calendar
```

見つかったコマンドは次のように実行できる。

```bash
obsidian command id="<command-id>"
```

これはカレンダー画面を開く、同期する、といったObsidianコマンドの実行に向いている。

---

## 3. JavaScript APIを使う

より細かい操作が必要なら、Obsidian CLIの `eval` からFCRのJavaScript APIを利用できる。

FCR APIの入口：

```javascript
app.plugins.plugins['full-calendar'].api
```

代表的な操作：

```text
getEvents()
createEvent()
updateEvent()
deleteEvent()
moveEvent()
getCalendarSources()
```

Obsidian CLIからJavaScriptを実行する場合：

```bash
obsidian eval code="<JavaScript>"
```

APIの正確な引数は、使用時点のFCR API仕様を確認すること。

---

## Codexへの運用指示

予定を扱うときは次の原則に従う。

- 予定の読み取りだけなら、まずFCR APIを使用する。
    
- 予定を追加・変更・削除するときも、可能ならFCR APIを使用する。
    
- FCR管理下のMarkdownを不用意に直接書き換えない。
    
- 不明な `calendarId` やイベントIDを推測しない。先に取得する。
    
- 複数件を変更する場合は、最初に現在の予定を確認する。
    
- 大量削除・大量変更は、実行前に対象を明確にする。
    
- APIトークンなどの秘密情報をノートへ直接記録しない。
    

## 想定する使い方

例えばCodexに、

> 9月10日の15時から16時に「買い物」という予定を入れて。

と依頼する。

Codexは、

```text
依頼
 ↓
現在のカレンダー情報を確認
 ↓
対象calendarIdを特定
 ↓
FCR APIで予定作成
 ↓
作成結果を確認
```

という手順で処理する。

人間はFull CalendarのGUIから、CodexはAPIから操作することで、同じ予定表を共有できる。