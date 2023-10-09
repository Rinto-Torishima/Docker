# Docker
このリポジトリをクローンするとDockerでlaravel10の開発環境を作ることができます。

## git cloneした際の環境構築方法
* コマンドプロンプトを開き、任意の場所でgit cloneする
```
git clone  https://github.com/Rinto-Torishima/Docker
```
* フォルダの名前をdockerに変更する
* docker-compose.ymlを置いたディレクトリに移動
```
cd docker/sns
```
* Docker 起動
```
docker-compose up -d
```
* appコンテナ（名称：laravel_app）に入ります
```
winpty docker-compose exec app bash
```
* Laravelプロジェクト移動
```
cd snsapp
```
* ストレージの権限変更
```
chmod 777 -R storage/
```
* .envファイルを作成
```
cp .env.exmaple .env
```
* .envファイルを編集
```
DB_HOST=laravel_db
```
//docker-compose.ymlの定義に合わせる。
```
DB_DATABASE=laravel_db
```
//docker-compose.ymlのmysql.environment.MYSQL_DATABASEの値を設定
```
DB_USERNAME=laravel_user
```
//docker-compose.ymlのmysql.environment.MYSQL_USERの値を設定
```
DB_PASSWORD=laravel_pass
```
//docker-compose.ymlのmysql.environment.MYSQL_PASSWORDの値を設定

* Composerのパッケージのインストール
```
composer install
```
* APP_KEYを更新
```
php artisan key:generate
```
* テーブルを作成
```
php artisan migrate
```
* npmでパッケージをインストール
```
npm install
```
* Laravel-Mixのビルド(開発環境なのでdevを指定)
```
npm run dev
```
* ブラウザでLaravelの初期ページにアクセスする
```
http://localhost
```
//初期画面が表示されたらOKです
