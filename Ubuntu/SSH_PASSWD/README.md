# Dockerfile使用方法
<a id="markdown-dockerfile%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95" name="dockerfile%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95"></a>

<!-- TOC -->

- [1. Dockerfile使用方法](#1-dockerfile%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95)
    - [1.1. コンテナ実行](#11-%E3%82%B3%E3%83%B3%E3%83%86%E3%83%8A%E5%AE%9F%E8%A1%8C)
    - [1.2. SSH接続](#12-ssh%E6%8E%A5%E7%B6%9A)

<!-- /TOC -->

## コンテナ実行
<a id="markdown-%E3%82%B3%E3%83%B3%E3%83%86%E3%83%8A%E5%AE%9F%E8%A1%8C" name="%E3%82%B3%E3%83%B3%E3%83%86%E3%83%8A%E5%AE%9F%E8%A1%8C"></a>

1. `docker build -t ubuntu18:ssh-passwd ./CentOS/SSH_PASSWD`
2. `docker images`コマンドで**IMAGE ID**を確認する。
3. `docker run`コマンドでコンテナを実行する。

```bash
$ docker run -itd -h <ホスト名> -p <ホスト側の空きポート>:22 <IMAGE ID or REPOSITORY:TAG>
```

## SSH接続
<a id="markdown-ssh%E6%8E%A5%E7%B6%9A" name="ssh%E6%8E%A5%E7%B6%9A"></a>

※ホストでの実行

```bash
$ ssh -p <コンテナ実行時に指定したポート番号> root@localhost