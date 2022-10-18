## Sample テーブルでの API ドキュメント

Airtable は API Docs https://airtable.com/api で、自分でつくった Base それぞれでの API でのアクセスの仕方を教えてくれます。

<img width="642" alt="image.png (38.7 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/df8ed6a4-89a5-4e66-bbbe-8e2e414868f9.png">

API Docs https://airtable.com/api にアクセスするとこのように表示されます。Sample をクリックしましょう。

Sample Base は [準備ページ](00-preparation.md) でつくった Sample Base です。

<img width="1920" alt="image.png (100.6 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/b4363606-8aa4-4eb5-b750-bfcdd1cbb719.png">

Sample テーブルでの API ドキュメントが表示されます。

### Base の ID を把握

<img width="1060" alt="image.png (65.3 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/647be72a-e479-4d37-bb25-a44fcbb43fc3.png">

Base は見た目上の名前「Sample」と違って、API でアクセスするときの ID が別にあります。今後プログラムで使うので意識しておきましょう。

## airtable モジュールの準備

Visual Studio Code で Airtable を動かすモジュールをインストールしておきます。

```
npm i airtable
```

## Name フィールドのデータ一覧表示

<img width="1920" alt="image.png (166.0 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/8a36a5de-e1c8-41cb-8bfa-6f43c39e86a6.png">

左メニューで List records をクリックして、右側の curl , JavaScript のところを JavaScript をクリックするとサンプルコードが表示されます。

CODE の部分を Visual Studio Code で list.js というファイルを作成してコピーアンドペーストします。

```js
var Airtable = require('airtable');
var base = new Airtable({apiKey: 'YOUR_API_KEY'}).base('****************');

base('Table 1').select({
    // Selecting the first 3 records in Grid view:
    maxRecords: 3,
    view: "Grid view"
}).eachPage(function page(records, fetchNextPage) {
    // This function (`page`) will get called for each page of records.

    records.forEach(function(record) {
        console.log('Retrieved', record.get('Name'));
    });

    // To fetch the next page of records, call `fetchNextPage`.
    // If there are more records, `page` will get called again.
    // If there are no more records, `done` will get called.
    fetchNextPage();

}, function done(err) {
    if (err) { console.error(err); return; }
});
```

TODO : 解説を書く

### API Key の反映

コピーアンドペーストできたら、`{apiKey: 'YOUR_API_KEY'}` の YOUR_API_KEY の部分を、先ほどメモした API Key に置き換えます。

### 実行してみる

```
node list.js
```

設定できたら list.js を実行してみましょう。

Retrieved 1
Retrieved 2
Retrieved 3

このように表示され、データが取得されていることが確認できます。

## Name フィールドのデータ検索

データの検索は filterByFormula というパラメータで行えます。Formula field reference https://support.airtable.com/docs/formula-field-reference に記法が書いてあります。

今回は Name フィールドで2の値のものを検索するようにしてみます。これは {Name}=2 と書きます。

```js
base('Table 1').select({
    // Selecting the first 3 records in Grid view:
    maxRecords: 3,
    view: "Grid view"
})
```

の部分を

```js
base('Table 1').select({
    // Selecting the first 3 records in Grid view:
    maxRecords: 3,
    view: "Grid view",
    filterByFormula: "{Name}=2"
})
```

に変更します。

```
node list.js
```

で実行してみると `Retrieved 2` と、Name が 2 だけ検索されます。

### Name 以外のデータ Notes も見てみる

```js
    records.forEach(function(record) {
        console.log('Retrieved', record.get('Name'));
    });
```

の部分を、

```js
    records.forEach(function(record) {
        console.log('Name', record.get('Name'));
        console.log('Notes', record.get('Notes'));
    });
```

に変更します。こうすることで Notes のデータも見ることができます。

```
node list.js
```

で実行してみると

```
Name 2
Notes データ B
```

と Notes も取得することができます。

## データの追加

データの追加をしてみましょう。

<img width="1920" alt="image.png (159.8 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/d5e19eba-2798-4383-98bd-14d441214657.png">

左メニューの Create fields をクリックするとデータの追加のドキュメントを見ることができます。

Visual Studio Code で create.js を作成して、CODE を参考に、このようなコードを試してみましょう。

```js
var Airtable = require('airtable');
var base = new Airtable({apiKey: 'YOUR_API_KEY'}).base('*********');

base('Table 1').create([
  {
    "fields": {
      "Name": "新しく追加されたデータです！",
      "Notes": "複数行も追加してみました！"
    }
  }
], function(err, records) {
  if (err) {
    console.error(err);
    return;
  }
  records.forEach(function (record) {
    console.log(record.getId());
  });
});
```

list.js を参考に `var base = new Airtable({apiKey: 'YOUR_API_KEY'}).base('*********');` の部分を、YOUR_API_KEYは API Key を、base の ********* の部分は BASE ID を置き換えましょう。

```
node create.js 
```

で実行してみます。

<img width="451" alt="image.png (4.2 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/7fde514a-3b21-4c09-9ea8-979a654475e3.png">

ターミナル側では、記録された行の ID (recordId）が返ってきます。

<img width="486" alt="image.png (16.0 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/8596d95e-8fca-4d9b-a3cf-165bd9956caf.png">

Airtable の Web 側で Sample の Table 1 のデータを確認してみると無事 4 番目に Name と Notes が登録されています。