# Apr13 workshop
-----
# Intro

## 今後の勉強会予定

## 目指すスキルセット：SRE

https://landing.google.com/sre/book.html

http://qiita.com/t2y/items/99e40560a67b76ea1ff5

## Plan

- ターゲットノード構成
- ネットワーク
- ユーザ

-----

# 環境準備

## Proxyの設定（Ansibleサーバ）
とりあえず
```
$ export http_proxy=http://<Proxyアドレス>:<ポート>
$ export https_proxy=http://<Proxyアドレス>:<ポート>
```

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

## パスワード無しでsudoできるようにする

***セキュリティ面で要検討***

ターゲットノードで
```
$ sudo visudo
```
最終行に追記
```
<ユーザ名> ALL=NOPASSWD: ALL
```

-----

# Playbookの構造

## inventory

`inventory/group_inventory.ini`

## 単純なPlaybook

`test_playbook.yml` : /etc/hostsを$HOME/tmpにコピる

実行
```
$ ansible-playbook -i group_inventory.ini ./test_playbook.yml
```

## role

`roles/proxy/tasks/main.yml` : Proxyを設定するロールタスク

`roles/proxy/vars/main.yml` : ロール内で使われる変数

## Ansible Galaxy

https://galaxy.ansible.com/

`roles/andrewrothstein.wildfly` : wildflyをインストール
