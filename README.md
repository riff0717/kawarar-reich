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
Local マシンで下記コマンドでnodeのデモ用サーバをpull
```
docker pull node
docker run --rm -it -v ${PWD}:/home/app -w /home/app node yarn create next-app --example blog-starter kawarar-reich
cd kawarar-reich
docker run --rm -it -v ${PWD}:/home/app -w /home/app -p 3000:3000 node yarn dev
```

# サーバの構築

```bash
sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine docker-engine-selinux
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install -y docker-ce docker-ce-cli containerd.io
[root@stg-app01 ~]# getenforce
Disabled
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
sudo yum install -y docker-ce docker-ce-cli containerd.io
[root@stg-app01 ~]# docker --version
Docker version 20.10.22, build 3a2c30b
systemctl start docker
systemctl enable docker
curl -L https://github.com/docker/compose/releases/download/v2.3.3/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
[root@stg-app01 ~]# docker-compose version
Docker Compose version v2.3.3
```

# 初回設定
初回はnode_modulesがないのでdocker-composeが失敗するため、git cloneした後の初回構築時のみ下記コマンドを実行する
`docker-compose run -w /home/app --rm app yarn install

> see https://zenn.dev/ttani/articles/docker-clone-first-operation

# 参考サイト
## 初期設定
[エンジニアなら自分でブログを作れ！①導入編](https://zenn.dev/miketako3/articles/9b2b1a9ec13901)

