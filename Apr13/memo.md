# Apr13 workshop
-----

# Plan

- ターゲットノード構成
- ネットワーク
- ユーザ

# 環境準備

# 

## ターゲットノードの作成

## SSH通信のための公開鍵設定

コントロールノードで

```
$ ssh-keygen -t rsa
$ ssh-copy-id -o StrictHostKeyChecking=no -i $HOME/.ssh/id_rsa.pub localhost
$ ssh-copy-id -o StrictHostKeyChecking=no -i $HOME/.ssh/id_rsa.pub <ターゲットノード>
```

確認
```
$ ssh <ターゲットノード>
```
