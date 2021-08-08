# DynamoDB Local

## 使い方

- port 8000で動作する
- 確認用のGUIは
  ```
  http://localhost:8000/shell
  ```

## aws-cliでの確認

```
aws dynamodb list-tables --endpoint-url http://localhost:8000
```

## 注意点

- DynamoDB Localの本体は http://s3-ap-northeast-1.amazonaws.com/dynamodb-local-tokyo/dynamodb_local_latest.tar.gz
- alpine 3.6にopenjdkをインストールして動かすだけだと、以下のエラーを起こす
  ```
  DynamoDBLocal_lib/libsqlite4java-linux-amd64.so: __memcpy_chk: symbol not found
  ```
- patchをあてたDynamoDB Localがあるので、それを持ってくる
  ```
  https://github.com/bhuisgen/docker-alpine/tree/master/alpine-dynamodb/rootfs/usr/local/dynamodb/DynamoDBLocal_lib
  ```
