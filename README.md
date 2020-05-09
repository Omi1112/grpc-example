# gRPC

## 概要

APIは、JSON形式で応答するAPIが一般的。
マイクロサービスを考えた時に機能ごとにAPIを作っていく考えだが、
サービス間通信をJSON形式のような文字列（テキスト）データでやりとりすると、
通信量が膨大になり遅延につながる。
そのため、バイナリデータへ変換して、通信できる仕組みが必要と考えられる。

この時の一つの手法として、
gRPCが存在する。

## 通信方法

gRPCは、WebAPIと異なり、
CURLコマンドで、URLを叩いて動作確認などの方法を今のところ知らない。

Go限定かもしれないが、protoファイルと呼ばれるインターフェースを定義するファイルをもとに、
XXXX.pg.goファイルを作成し、
このファイルを基にサーバー側クライアント側で通信が行えるようになる。

## pgファイルの作成方法

まず初めに、.proto ファイルを作成する。
詳細は、example/example.protoを参照。

以下コマンドでXXXX.pg.goファイルを作成する。

```
protoc -I example/ example/example.proto --go_out=plugins=grpc:example
```

このコマンドを実行すると、/example/SeijiOmi/go-example/example/example.pb.go
フォルダ配下にXXXX.example.pg.goファイルが生成される。
これを回避する方法は、今のところ見当たらないため、生成された、XXXX.example.pg.goファイルを
/example　に移動し、includeする。
