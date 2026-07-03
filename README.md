# Bot投稿ルール一覧ダッシュボード

ワイズグループの社内Botが「いつ・どのSlackチャンネルに・何を」投稿しているかの全体図・一覧。

- **公開URL:** https://wiseinc-pharmacy.github.io/bot-channel-map/
- **アクセス制御:** Googleログイン（`allowlist.json` の名簿に載ったアカウントのみ閲覧可）
- **認証:** Firebase Auth（wise-budget-26d4c を認証にのみ流用。Firestoreは不使用）

## 閲覧できる人を増やす

`allowlist.json` の `allowed` にメールアドレス（Googleアカウント）を追加して push すれば反映されます。

```json
{
  "allowed": [
    "director@wise-jmco.com",
    "info@wise-jmco.com"
  ]
}
```

## 注意

- 静的サイト（GitHub Pages）のため、ログインは「画面の目隠し」です。ページのソースには埋め込みデータ（チャンネルID・Bot名）が含まれます。トークン・パスワードは一切含みません。
- 投稿ルールの元データは各Botのソースコード実装（`monthly_reminder.mjs` / `gmail_to_slack.mjs` / `recruit_bot.mjs` / `accounts_bot.mjs` / `hakase_bot.mjs` / `dev_kun.mjs` 等）に基づく手動集計。Botの改修時は本ダッシュボードの `RULES` 配列も更新すること。
