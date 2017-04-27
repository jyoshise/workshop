# Apr 27 workshop
------

## インフラチーム用環境の状況

## インベントリの書き方
- グループをネストした場合、同じホストに対する実行は一回だけになってしまう。

## リスト変数

- `inventory/yoshise_azure.ini` のホスト変数の書き方
- `playbooks/test_playbook`での`with_items`の使い方

## インベントリファイルの分け方
- 環境（本番/検証/開発/インフラ開発/etc）で分けるのが間違いがない

## 変数を定義する場所
以下本番/検証/開発の区別を"ステージ"、AP/DB/Batchの区別を"サーバ役割"、LE/LX/LJなどを"インスタンス種別"として
- `inventory/group_vars/all.yml` ステージ、サーバ役割、インスタンス種別によらずすべての対象に対して適用される値
- `inventory/group_vars/<サーバ種別>.yml` 全ステージ、全インスタンスで共通だが、サーバ役割に固有の値
- `inventory/host_vars/<ホスト>.yml` 個別のホストに対して設定する値。そのホストに乗るインスタンスは、ここから後述のinstance_varsを参照する？1ホストに複数インスタンスが乗る場合もあるので、リスト変数とする？

- `inventory/instance_vars/<インスタンス>.yml` インスタンス名に紐づく値はここに書く？
- `inventory/<ステージ>.ini` 各ステージに固有の値