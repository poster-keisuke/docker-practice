## ディレクトリ構造

```
node
├─ project
│   ├─ app ←（コンテナによって作成される）
│   ├─ Dockerfile
└─ docker-compose.yml
```

## 手順書

### Dockerfileからイメージをビルド(初回起動時のみ) 
`$ docker-compose build` 

以下のimagesが表示されていればOK

`$ docker images`
```
node-express-dev    1.0                 80e3ab7a96fb        1 minutes ago       70.8MB
node                10.13.0-alpine      e35872f034fd        1 minutes ago        70.2MB
```

### コンテナの作成

`$ docker-compose up -d //-d デーモンとして起動`

### 状態の確認

`$ docker-compose ps`

以下のプロセスが立ち上がっていたら成功

```
Name   Command   State           Ports
-----------------------------------------------
node   node      Up      0.0.0.0:8080->3000/tcp
```

### コンテナ内に入る

`$ docker exec -it node /bin/sh`

`$ node -v`

バージョンが表示されていればOK
```
v10.13.0
```