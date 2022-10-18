# LINE Notify 初期設定

LINE Notify のトークンを取得します。

## LINE アカウント事前確認

まず、LINE アカウント確認です。

<img src="https://guide.line.me/ja/install_5.png" width="200" />

LINE アカウントとスマホアプリインストールを確認します。

## LINE Notify サイトログイン

LINE Notify サイトにログインしアカウント確認をします。

![image](https://i.gyazo.com/c45ee309aa6793bc12f67c24f3a905ce.png)

https://notify-bot.line.me/ja/ に、まずアクセスします。

![image](https://i.gyazo.com/043d433bfa913e2edaee4bb917e92bb2.png)

右上のログインをクリック。

![image](https://i.gyazo.com/d2a7444465cb56a81eedb3e957403806.png)

下部の QR コードログインをクリックします。（メールアドレス・パスワードは、おそらくみなさん設定していないのと、いまから設定をやるとなると、PCとアプリを行き来して、まあまあ大変になるので今回は避けます。）

![image](https://i.gyazo.com/a6834bc86db3d0f024a0cb5886664883.png)

QR コードが表示されます。 LINE アプリでスキャンするとログインできます。QR コードのスキャン方法は「QR コードのスキャン方法はこちら」のリンクをクリックすると表示されます。

![image](https://i.gyazo.com/e3856b10d3a1b933f284f7f81f3fac64.png)

QR コードのスキャン方法については、このようになっています。

![image](https://i.gyazo.com/bf26cdcf093a783aee4ff510ec9ddb68.png)

ログインすると、右上にアカウント名が出るのでクリックします。

![image](https://i.gyazo.com/7cdb07c7e588bac278a5fb0b2dbc9d83.png)

マイページをクリック。

![image](https://i.gyazo.com/0c48f49af1be4e5e7c789366c0b838cf.png)

マイページの下の方に「アクセストークンの発行(開発者向け)」というエリアがあるのでスクロールします。

![image](https://i.gyazo.com/bbba9909e0437e487718479953b198ff.png)

トークンを発行するボタンをクリックします。

![image](https://i.gyazo.com/b0b76e806cffea8f03cfec5f789d9866.png)

トークンを発行するウィンドウが表示されるので、以下のように対応します。

- トークン名を記入してください (通知の際に表示されます)
  - `My Notify` と入力（自分が分かる自由な名前でかまいません）
- 通知を送信するトークルームを選択してください
  - `1:1でLINE Notifyから通知を受け取る` を選択

こちらを対応すると、発行するボタンが押せるようになるのでクリックします。

![image](https://i.gyazo.com/abee7f38d2db6897c61cdb42fc29a83c.png)

このようにトークンが表示されるのでメモしましょう。

**このページから移動すると、新しく発行されたトークンは二度と表示されないので気をつけましょう**

メモしたらウィンドウを閉じるボタンをクリックして閉じます。

![image](https://i.gyazo.com/2fcf2f7f0d039737510759301a619485.png)

リストに追加されたことを確認しておきます。

![image](https://i.gyazo.com/07a33eec5562fc6fd67e52aeaa5c2bc9.png)

今回選択した LINE Notify 先のアカウントにこのようなメッセージが来ていることも確認します。