## 初回の起動
```
docker-compose up -d

# コンポーザー
docker-compose exec app composer -v
docker-compose exec app composer update
docker-compose exec app composer install
cp src/.env.example src/.env
docker-compose exec app php artisan key:generate

# React Dev
docker-compose exec app npm install
docker-compose exec app npm run dev
```

## 解説記事
### 前編（バックエンド）
https://sagara.ink/article/app/204/

### 後編（フロントエンド）
https://sagara.ink/article/app/205/

## 1. Docker
### 1-1. Nginx
Nginxのコンテナを構築してブラウザでHTMLを表示するまで
### 1-2. PHP
PHPのコンテナを構築してブラウザでphpinfoを表示するまで
### 1-3. MySQL
MySQLのコンテナを構築してブラウザでPHPMyAdminを表示するまで
## 2. Laravel
### 2-1. Composer
Composerを使えるようにするまで
### 2-2. Laravel
ブラウザでLaravelの初期画面表示するまで
## 3. React
### 3-1. Node
Nodeとnpmを使えるようにするまで
### 3-2. Mix
ブラウザにReactコンポーネントを表示するまで
## 4. TypeScript
### 4-1. TypeScript
TypeScriptを使えるようにするまで




```
docker-compose down
docker-compose rm -f $(docker ps -aq)
docker-compose rmi -f $(docker images -aq)
docker-compose build
docker-compose up -d
docker-compose exec app sh
```
```
初回実行に必要なコマンド
composer install

全てのテーブルを削除してからマイグレーションシーダー
php artisan migrate:fresh --seed

全てのテーブルを削除してからマイグレーション
php artisan migrate:fresh

テーブルをつくる
php artisan make:migration create_users_table

コンフィグリセット
php artisan config:cache

コントローラー作成
php artisan make:controller ApiController
```
https://sagara.ink/article/app/205/
