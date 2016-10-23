

## 概要

nginxで画像をリサイズするサンプル

## 準備

```
- OSXのバージョン
$ sw_vers
ProductName:	Mac OS X
ProductVersion:	10.11.6
BuildVersion:	15G31
```

```
- Docker for Mac
$ docker --version
Docker version 1.12.1, build 6f9534c

下記からインストール
https://docs.docker.com/docker-for-mac/
```

## 使い方

```
# ビルド(初回のみ)
$ docker-compose build

# サーバ起動(毎回)
$ docker-compose up -d

# サーバ停止(毎回)
$ docker-compose stop
```

適当な画像を`./nginx/images`に配置する  



## 参考

- http://cloudrop.jp/labs/nginx_image_filter
