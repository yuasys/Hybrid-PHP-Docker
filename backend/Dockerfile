FROM php:8.2-apache

# 必要なパッケージ、Vim、SQLite3のインストール
RUN apt-get update && apt-get install -y \
    vim \
    sqlite3 \
    libsqlite3-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# PHPのSQLite接続拡張機能を有効化
RUN docker-php-ext-install pdo pdo_sqlite

# ApacheのRewriteモジュールを有効化（REST APIのルーティング用）
RUN a2enmod rewrite

# SQLiteデータベース配置用のディレクトリ作成と権限変更
RUN mkdir -p /var/www/db && chown -R www-data:www-data /var/www/db

WORKDIR /var/www/htm