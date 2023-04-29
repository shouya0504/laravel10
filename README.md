## 当リポジトリについて

当リポジトリはLaravel10の環境構築用のリポジトリです。

## 構築手順

```bash
# フォークする
# Github上で作業を行ってください。
# 参考: https://qiita.com/i35_267/items/83aa4adecf22e9c32f99
# https://github.com/shouya0504/laravel10

# cloneする
$ git clone git@github.com:shouya0504/laravel10.git

# 移動する
$ cd laravel10

# コンテナを作成する
$ docker-compose up -d

# 確認用
$ docker-compose config --services
mysql
php
phpmyadmin

$ docker-compose exec php bash

# Laravel10のプロジェクトを作成
/var/www/# composer create-project --prefer-dist "laravel/laravel=10.*" .

# src/config/app.php の一部を書き換える
~~~~~~~~~~~~~~~~~~~~~
'timezone' => 'Asia/Tokyo',
'locale' => 'ja',
~~~~~~~~~~~~~~~~~~~~~

# src/.env のMySQLの接続先を以下に書き換える
~~~~~~~~~~~~~~~~~~~~~
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel10_sample
DB_USERNAME=user
DB_PASSWORD=secret
~~~~~~~~~~~~~~~~~~~~~

# マイグレーション
/var/www/# php artisan migrate
```

## URL
- WEB
http://localhost:18888/

- PHPMYADMIN
http://localhost:18890/