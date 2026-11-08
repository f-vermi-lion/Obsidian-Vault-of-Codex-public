# Obsidian-Vault-of-Codex-public

CodexのAstraがMinecraft Java版を長時間プレイした実験で、参照・更新したObsidian書庫の公開用アーカイブです。計画、観測、失敗、判断の変化を、ノートとGit履歴から追えるようにしています。

**Minecraftの公式資料ではなく、MojangまたはMicrosoftの承認・提携を受けたものではありません。**

> NOT AN OFFICIAL MINECRAFT PUBLICATION. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.

発行者・本アーカイブの責任者：**f-vermi-lion**。連絡先：[f.vermilion.github@gmail.com](mailto:f.vermilion.github@gmail.com)。

## 読み始める場所

- [攻略の現在地](Minecraft攻略の現在地.md)：収録時点の到達点と再開の導線。
- [エンダードラゴン攻略の目的と計画](P文書/Minecraftエンドラ攻略.md)：取り組み全体の方針。
- [書庫の使い方に関する初期の助言](この書庫の使い方についてのユーザーからの初期の助言.md)：書庫を使う意図。
- [AGENTS.md](AGENTS.md)：実験中の書庫運用指示。過去の実験環境に向けた記録です。
- [images/](images/)：ノートに対応する画面画像とarc42の図。

ノートには当時の誤認や後から修正された判断も含みます。記録の意味は、その時点のノートと後続の更新を合わせて確認してください。このリポジトリ単体に、セッションログ、操作基盤、動画、ワールドのすべてが含まれているわけではありません。

通常のMarkdownはGitHubで読めます。`[[ノート名]]` や `![[画像名]]` などのObsidian記法を含むため、書庫として閲覧する場合はローカルに取得したフォルダをObsidianで開いてください。元の`.obsidian/`設定・プラグインは含めていません。書庫内のコマンド例や運用指示を、現在の環境で自動実行する必要はありません。

## 履歴と公開用の加工

`master`は、加工済み実験履歴の末尾に公開説明を追加したブランチです。記録保持用の`backup-2026-09-24`、`codex/astra-vault-routing`、`snapshot-2026-10-09-cleared-minecraft`は、加工済みコピーの状態を保持しています。

原本を保全し、公開用コピーに以下の加工を行いました。

| 加工・保全 | 内容 |
|---|---|
| 設定の除外 | `.obsidian/`を全履歴から除外 |
| 作者メール | 指定された1種類・4出現を一貫した仮名メールへ置換 |
| 署名 | 履歴変更により無効になるコミット署名1件を除去 |
| 実験の記録 | 元の505コミットを一対一で保持。親子関係・日時・メッセージを保全 |
| ノート・画像 | 保持対象2,098種類のファイル内容は不変。うち画像913種類 |
| 公開用の追加 | `master`にこのREADME、権利表示、加工説明とライセンス本文を追加。`.gitignore`で`.obsidian/`全体を除外 |

履歴を書き換えたため原本とコミットIDは異なります。詳しい変更範囲、検証、参照の扱いは[加工説明](PROCESSING.md)を参照してください。

## 利用条件・権利

**リポジトリ全体を一律にCC0とするものではありません。** [権利表示の全文](LICENSE.md)と[第三者資料の出典](THIRD_PARTY_NOTICES.md)を合わせて確認してください。記録保持用ブランチや過去の版から資料を取り出す場合も同じ区別が必要です。

| 対象 | 扱い |
|---|---|
| 公開者が権利を持つノート・記録・追加文書等 | その権利を持つ範囲でCC0 1.0 Universal |
| Codexが生成した文章 | 著作権の有無を一括して断定しない。公開者に権利がある場合は上記CC0の対象 |
| Minecraftの画面に含まれるゲーム素材・商標等 | Mojang / Microsoft等の権利を保持。CC0の対象外。公式EULA・Usage Guidelines等を参照 |
| arc42テンプレート・図 | CC BY-SA 4.0。著作者・出典・ライセンス表示を保持 |
| その他の引用・第三者素材 | それぞれの権利・条件に従う。公開者のCC0で第三者の権利を許諾しない |

**Rights summary (English):** The publisher applies CC0 1.0 only to rights they hold. This does not declare all AI-generated text copyrightable. Minecraft content and other third-party rights are excluded; arc42 material is under CC BY-SA 4.0. See [LICENSE.md](LICENSE.md) and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
