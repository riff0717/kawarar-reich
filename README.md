# kawarar-reich
kawarar-reich-pjとして作成中

# 開発環境構築
Windows + WSL2 Ubunt + Docker Desktop

```
docker-compose build --no-cache
docker-compose up
```

access : http://localhost:3000/

## 初期構築手順
Dockerファイルを作成するまでにやったこと
```
docker pull node
docker run --rm -it -v ${PWD}:/home/app -w /home/app node yarn create next-app --example blog-starter kawarar-reich
cd kawarar-reich
docker run --rm -it -v ${PWD}:/home/app -w /home/app -p 3000:3000 node yarn dev
```

# 参考サイト
## 初期設定
[エンジニアなら自分でブログを作れ！①導入編](https://zenn.dev/miketako3/articles/9b2b1a9ec13901)

