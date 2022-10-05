# アイデアソン enebular ご紹介

みなさん、こんにちは！

テクニカルメンターから enebular についてご紹介します。

## enebular とは

> ![image](https://i.gyazo.com/627c47635133e03b57279d3292cdbf29.png)
> 
> enebular  
> https://www.enebular.com/ja/

あらゆるデバイスとクラウドサービスを「つなぐ」、IoT のためのデータ連携プラットフォームです。アカウント登録をすることで無料で始められます。

HTTP でつながる様々な API サービスとつながります。今回のハッカソンで扱う LINE やメタデータの API へも、もちろんつながります。

enebular のドキュメントはこちらです。

![image](https://i.gyazo.com/e6044a271c9e7913c5a34a378a8ed48b.png)

> Introduction · enebular  
> https://docs.enebular.com/ja/

## Node-RED というローコードツールがベース

enebular は Node-RED というローコードツールがベースにあります。

ローコードツールとは、あまりプログラムを書かずに、目で見て機能をポチポチつなぐ操作で、仕組みが作れるツールの総称です。そのうちのひとつが Node-RED です。

![image](https://i.gyazo.com/a93a65feb868db86c580e9f495d8a9e0.png)

enebular ではノードという機能のかたまりをつないで、フローというデータの流れを作り、データや IoT につながります。

![image](https://i.gyazo.com/82277372eeca4580a378bbc8bcc97769.jpg)

たとえば、このようなフローで柴犬画像を返してくれる API に HTTP でつないで画像を表示する仕組みがすぐに作れます。

プログラムを書いた経験があまりなくてもノードの機能を試して理解しながらつなげば、仕組みがつくれます。

![image](https://i.gyazo.com/0f0d8330e70baee4b216f55c51881f0b.png)

Node-RED の詳しい使い方は Node-RED の日本のコミュニティページを見てみると良いでしょう。

> ドキュメント : Node-RED日本ユーザ会  
> https://nodered.jp/docs/

## チームでの共同作業や試行錯誤にも寄り添う

![image](https://i.gyazo.com/9b56c44bc03f5f4d2262903e1d1cfef8.png)

enebular には、複数フローの管理、共有が可能であったり、特定ユーザーとのノード共有機能であったり Node-RED をより便利にする機能があります。ハッカソンでのトライアンドエラーをフローで管理してチーム内で共有して進めることができますね。

参考文献
> 複数デバイス管理（enebular連携編） | ia-cloud/Node-RED スクール  
> https://node-red.ia-cloud.com/enebular

## クラウド実行環境

> ![](https://blog.enebular.com/wp-content/uploads/2022/03/image-1-768x310.png)
>
> 新リリースのenebularクラウド実行環境の使い方 | enebular blog  
https://blog.enebular.com/enebular/how-to-use-enebular-cloud-exec-environment/

作ったフローを、一定時間で何かをしたり、HTTP でアクセスした時だけ仕組みが動くような環境「実行環境」も構築できます。

## ハッカソンでこんな風に使える

![image](https://i.gyazo.com/5cecb4da5090e7290bc69bd3f5eb059e.png)

ハッカソンでは、使い方次第で以下のように使えます。

- LINE BOT や LINE Notify の仕組みを enebular でつくって動かす
- メタデータ API からつないでメタデータと他の仕組みと連携する
- M5Stack からデータを受け取って LINE Notify に通知する

## 参考文献

![image](https://i.gyazo.com/48a29e0bbec328b7ab43b0e7f39e59b4.png)

（随時追加）