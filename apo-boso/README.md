# 房総apo

GitHub Pages と Google Apps Script だけで動かす、房総版のアポイント管理アプリです。

## 配置するファイル

GitHub Pages には次の2ファイルをアップロードします。

- `apo-boso/index.html`
- `apo-boso/site-config.js`

Apps Script はFAS本体と共用します。ルートの `GAS_code.js` の内容を貼り付けて、Webアプリとしてデプロイします。

## 初期設定

1. ルートの `GAS_code.js` の `SHEET_ID` を房総用スプレッドシートIDにします。
2. Apps Script を Web アプリとしてデプロイします。
   - 実行ユーザー: 自分
   - アクセスできるユーザー: 全員
3. 発行された `/exec` URL をルートの `site-config.js` の `BOSO_GAS_URL` に設定します。
4. GitHub Pages のURLで `apo-boso/` を開きます。

## データ保存先

GASはスプレッドシート内に次のシートを自動作成します。

- `apo_アポインター`
- `apo_実績`
- `apo_ログ`

## 初期アポインター

`apo_アポインター` シートを初めて作成するとき、同じスプレッドシート内のFASプランナー一覧を初期アポインターとして自動登録します。
既に `apo_アポインター` シートにデータがある場合は上書きしません。

アポインター管理タブの `FASプランナー読込` は、GitHub Pages上の `planners.json` から未登録者だけを追加する補助機能です。
