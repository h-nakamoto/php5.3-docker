# php5.3-docker
Cent OS + php-5.3を再現するDocker環境です。

## マウント構成
構成はこの環境と並列にソースコードが展開されていることを前提としています。
docker-compose.ymlの`./SRC`部分を、ソースコードを展開したテストパスに置き換えください。

├ SRC
└ php5.3-docker

```
 - ../SRC:/var/www/html/public
```

## コンテナイメージ
| コンテナ | サービス名 | Image | 出力ポート |
| --------- | ------------ | ----- | ------------ |
| php:5.3-apache | php | PHP-5.3(Cent OS) | http://localhost:17580|
| httpd | httpd | PHP/Apacheのログ | http://localhost:17581 |
| dozzle | dozzle | Docker コンテナ起動ログ | http://localhost:17582 |

