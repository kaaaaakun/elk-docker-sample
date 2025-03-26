# Filebeat

Filebeat is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on your servers,
Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to
Elasticsearch or Logstash for indexing.

## Usage

**This extension requires the `filebeat_internal` and `beats_system` users to be created and initialized with a
password.** In case you haven't done that during the initial startup of the stack, please refer to [How to re-execute
the setup][setup] to run the setup container again and initialize these users.

To include Filebeat in the stack, run Docker Compose from the root of the repository with an additional command line
argument referencing the `filebeat-compose.yml` file:

```console
$ docker compose -f docker-compose.yml -f extensions/filebeat/filebeat-compose.yml up
```

## Configuring Filebeat

The Filebeat configuration is stored in [`config/filebeat.yml`](./config/filebeat.yml). You can modify this file with
the help of the [Configuration reference][filebeat-config].

Any change to the Filebeat configuration requires a restart of the Filebeat container:

```console
$ docker compose -f docker-compose.yml -f extensions/filebeat/filebeat-compose.yml restart filebeat
```

Please refer to the following documentation page for more details about how to configure Filebeat inside a Docker
container: [Run Filebeat on Docker][filebeat-docker].

## See also

[Filebeat documentation][filebeat-doc]

[filebeat-config]: https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-reference-yml.html
[filebeat-docker]: https://www.elastic.co/guide/en/beats/filebeat/current/running-on-docker.html
[filebeat-doc]: https://www.elastic.co/guide/en/beats/filebeat/current/index.html

[setup]: ../../README.md#how-to-re-execute-the-setup


# Filebeat

Filebeatは、ログデータを転送および集中管理するための軽量なシッパーです。サーバーにエージェントとしてインストールされ、指定したログファイルまたは場所を監視し、ログイベントを収集して、インデックス作成のためにElasticsearchまたはLogstashに転送します。

## 使用方法

**この拡張機能では、`filebeat_internal`および`beats_system`ユーザーが作成され、パスワードで初期化されている必要があります。** スタックの初期起動時にこれらを実行していない場合は、[セットアップの再実行方法][setup]を参照してセットアップコンテナを再度実行し、これらのユーザーを初期化してください。

スタックにFilebeatを含めるには、リポジトリのルートからDocker Composeを、`filebeat-compose.yml`ファイルを参照する追加のコマンドライン引数を付けて実行します。

```console
$ docker compose -f docker-compose.yml -f extensions/filebeat/filebeat-compose.yml up
```

## Filebeatの設定

Filebeatの設定は、[`config/filebeat.yml`](./config/filebeat.yml)に保存されています。[設定リファレンス][filebeat-config]を参照して、このファイルを修正できます。

Filebeatの設定を変更した場合は、Filebeatコンテナの再起動が必要です。

```console
$ docker compose -f docker-compose.yml -f extensions/filebeat/filebeat-compose.yml restart filebeat
```

Dockerコンテナ内でFilebeatを設定する方法の詳細については、次のドキュメントページを参照してください：[DockerでFilebeatを実行][filebeat-docker]。

## 関連情報

[Filebeatドキュメント][filebeat-doc]

[filebeat-config]: [https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-reference-yml.html](https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-reference-yml.html)
[filebeat-docker]: [https://www.elastic.co/guide/en/beats/filebeat/current/running-on-docker.html](https://www.elastic.co/guide/en/beats/filebeat/current/running-on-docker.html)
[filebeat-doc]: [https://www.elastic.co/guide/en/beats/filebeat/current/index.html](https://www.elastic.co/guide/en/beats/filebeat/current/index.html)

[setup]: ../../README.md#how-to-re-execute-the-setup
