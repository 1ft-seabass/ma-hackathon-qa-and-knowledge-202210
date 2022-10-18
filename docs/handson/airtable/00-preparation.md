# アカウント準備と API Key 準備

## Airtable というクラウド型データベース

Airtable https://www.airtable.com/ というクラウド型データベースを触ってみます。

![e5f34a332182a4e0a07abedd1354df68](https://i.gyazo.com/e5f34a332182a4e0a07abedd1354df68.png)

Google スプレッドシートのような見た目で Web から GUI でデータを作成・更新・削除・検索できます。また、API も充実していて使いやすくデータを操作することができます。

![3774deda3b412fb22b9e50b95d2e4a88](https://i.gyazo.com/3774deda3b412fb22b9e50b95d2e4a88.png)

2022 年 10 月現在 Pricing https://airtable.com/pricing を見てみると

　V 無制限の Base
　V Base あたり1,200レコード
　V Base あたり2GBの添付ファイル
　V グリッド、カレンダー、かんばん、フォーム、およびギャラリービュー

が無料枠で含まれるので、とりあえず触ってみても基本的な機能を体験しやすいものになっています。

## アカウント作成

サインアップ https://airtable.com/signup からアカウントを作成します。

![5935819c6b0614e99bf49787f06f9a98](https://i.gyazo.com/5935819c6b0614e99bf49787f06f9a98.png)

Work email にメールアドレスを入力しましょう。

<img width="700" alt="image.png (53.7 kB)" src="https://img.esa.io/uploads/production/attachments/3062/2022/09/05/8131/a695052f-b31c-44ff-8ef7-75c746d9da00.png">

Full name と Password を入力します。メールアドレスとパスワードはメモして控えておきましょう。

Continue ボタンをクリックします。

![7138ec5e9815e03d80a810121dff8d83](https://i.gyazo.com/7138ec5e9815e03d80a810121dff8d83.png)

どんなカテゴリにいるか聞かれるので、選択します。アンケート的なものです。

![c315736186693f7fdee818d4c3270134](https://i.gyazo.com/c315736186693f7fdee818d4c3270134.png)

ほかの人の招待は Skip します。

![3b1c04dbb6c8d0c52673a1623397f61e](https://i.gyazo.com/3b1c04dbb6c8d0c52673a1623397f61e.png)

なにかテスト的にはじめるデータを聞かれますが、今回は Skip で。

![d8ba36820f279c106c16c394346e8cf7](https://i.gyazo.com/d8ba36820f279c106c16c394346e8cf7.png)

Go to workspace をクリックします。

![5368bbecb3e4e92ca5edc8d5514d1b9a](https://i.gyazo.com/5368bbecb3e4e92ca5edc8d5514d1b9a.png)

Workspace に移動しました。

### Verify my email もチェックしておきましょう

![91b0725105e7b8d07e273c765b0a5f08](https://i.gyazo.com/91b0725105e7b8d07e273c765b0a5f08.png)

登録したメールアドレスに確認メール（Verify my email）が届くので Verify my email ボタンをクリックして、確認完了しておきましょう。

![bd9ab490b7d8f3bd523ee1dc17d0ed80](https://i.gyazo.com/bd9ab490b7d8f3bd523ee1dc17d0ed80.png)

Workspace に移動して Your email has been verified! と表示されたら対応 OK です。

## データのかたまり Base を準備する

AirTable ではスプレッドシートのようなデータのかたまりを Base と呼びます。

英語ですが、こちらの記事 Creating a new empty base https://support.airtable.com/docs/creating-a-new-empty-base も参考になります。

![cc65d34c9785489fa5c239ae5f421af1](https://i.gyazo.com/cc65d34c9785489fa5c239ae5f421af1.png)

Create a base ボタンをクリックします。

![c414c9006ccb306beb2bc646348f2068](https://i.gyazo.com/c414c9006ccb306beb2bc646348f2068.png)

さっそく Base が Untitleed Base として出来上がります。カラーはランダムです。

### すでにデータの入れ物（フィールド）は仮で用意されている

![8960a417a03773a65fd2a541dfd057ef](https://i.gyazo.com/8960a417a03773a65fd2a541dfd057ef.png)

Airtable は最初にとりあえず使えるデータの入れ物（フィールド）は用意されています。

- フィールド名 Name
    - フィールドタイプ Single text line（単一行）
- フィールド名 Notes
    - フィールドタイプ Long text（複数行）
- フィールド名 Assignee
    - フィールドタイプ User
- フィールド名 Status
    - フィールドタイプ Single select（単一選択）

今回は、これをこのまま使います。

データベースの機能で言うと、管理は Airtable 側がほとんど行ってくれていて、今回の Base ではデータ定義がすでに済んでいる状況です。みなさんは、データの操作に注力できます。

### データを簡単に作る

![1bfd92e11bfd63316cf82eb39dff4e66](https://i.gyazo.com/1bfd92e11bfd63316cf82eb39dff4e66.png)

Google スプレッドシートのような操作で、データ入力が行えます。

Name フィールドの1行目には1、2行目には2、3行目には3とデータを入力して準備しておきます。

Notes フィールドの1行目にはデータ A、2行目にはデータ B、3行目にはデータ Cとデータを入力して準備しておきます。

### Base 名を Sample としておきます

![8e4ba83ca996e6f986b364d8d9f2fff1](https://i.gyazo.com/8e4ba83ca996e6f986b364d8d9f2fff1.png)

左上の Unititled Base と表示されているところをクリックすると Base 名が変更できます。Sample としておきましょう。

### Table 名はそのまま

![bac06cb663e7bfddd141665b9ce1d9dd](https://i.gyazo.com/bac06cb663e7bfddd141665b9ce1d9dd.png)

左上に Table 1 というタブがありますが今回の Table 名です。このままにしておきます。

## アカウントページで API Key をメモする

アカウントでログインした状態で アカウントページ https://airtable.com/account に移動します。ブラウザで別タブでアクセスしましょう。

![393f9f4ff809ec417653533598577655](https://i.gyazo.com/393f9f4ff809ec417653533598577655.png)

アカウントページが表示されました。

![613183bdd8f381bf1ac5fe1fd13e96e4](https://i.gyazo.com/613183bdd8f381bf1ac5fe1fd13e96e4.png)

API 欄の Generate API Key ボタンをクリックします。Generate API Key は、一度だけの作業です。生成できたら、今後は生成された API Key を使います。

![7cc1f524bf2eaf614fe1abae858de1ea](https://i.gyazo.com/7cc1f524bf2eaf614fe1abae858de1ea.png)

生成されました。

![fc29fbe228d071d1fb75303fbb670542](https://i.gyazo.com/fc29fbe228d071d1fb75303fbb670542.png)

・・・・・で隠されたフィールドをクリックすると API Key が出てくるので、テキストエディタにメモしておきましょう。

## これで準備完了です

Airtable https://www.airtable.com/ でオンライン上からデータ入力や管理を行って、API Key を使って Node.js や Node-RED など他のプログラムからも API から操作できます！