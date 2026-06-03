FROM node:20-slim

# コンテナ内での作業用にVimをインストール
RUN apt-get update && apt-get install -y vim && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# コンテナ起動時に依存パッケージをインストール
COPY package*.json ./
RUN npm install

EXPOSE 5173