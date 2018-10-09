#  Docker Portfolio

## 前提条件
下記をインストール済み

- PhpStorm:2018.1.6
- Docker:18.03.1-ce
- Docker Compose:1.21.1

### 使用イメージ

- node:10.10.0-alpine → 80:8080

### その他

- docker-compose.yml:3.6

## 準備

```
# プロジェクトをクローン
git clone https://github.com/honwaka-developer/docker_portfolio

# イメージをインストール・ビルドしてコンテナを作成・起動
docker-compose up -d

docker-compose exec node /bin/sh

git submodule add https://github.com/honwaka-developer/honwaka-developer.github.io.git app/honwaka-developer.github.io

cd honwaka-developer.github.io

npm install

npm run serve

# localhost で確認
```

## その他

### 公式リファレンス

- [Node](https://docs.docker.com/samples/library/node/)

### 使用するであろうコマンド集

#### Docker Compose
- 対象（docker-compose.yml）からイメージをビルドしてコンテナを作成し、バックグラウンドで起動したままにする
```
docker-compose up -d
```

- up されたコンテナを停止して削除（「**--rmi all**」をつけるとイメージも削除する）
```
docker-compose down --rmi all
```

- 対象のコンテナを強制停止
```
docker-compose kill
```

- 対象のイメージを表示
```
docker-compose images
```

#### Docker
- コンテナを全て削除
```
docker rm $(docker ps -aq)
```

- 未使用イメージ全て削除
```
docker rmi $(docker images -q)
```