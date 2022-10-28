

.. note::

 | Exastro OASE をインストールする環境で、既にインストール済みのソフトウェアはスキップを行います。
 | 標準出力に下記のようにSKIP LISTが表示された場合は、スキップ処理が行われています。
 | その場合は「7. スキップ処理の確認」の手順を実施してください。

 .. code-block:: bash

  [2020-11-12 08:59:43] INFO : Finished to install
  [2020-11-12 08:59:43] #####################################
  [2020-11-12 08:59:43] SKIP LIST(Please check the Settings) 
  [2020-11-12 08:59:43] ・rabbitmq-server
  [2020-11-12 08:59:43] ・mariadb-server
  [2020-11-12 08:59:43] #####################################
  [2020-11-12 08:59:43] INFO : Install Finished
  [2020-11-12 08:59:43] #####################################


| 8. スキップ処理の確認
| RabbitMQ や MariaDB をスキップした場合は、Exastro OASE 用に設定が必要になります。

| 8.1 RabbitMQ
| Exastro OASE 用のユーザ作成を実施するため、以下のコマンドを実行してください。

| 1 ユーザ作成

.. code-block:: bash

 # rabbitmqctl add_user {RabbitMQ_username} {RabbitMQ_password}

| 2 ユーザの権限設定

.. code-block:: bash

 # rabbitmqctl set_user_tags {RabbitMQ_username} administrator

| 3 ユーザのパーミッション設定

.. code-block:: bash

 # rabbitmqctl set_permissions -p / {RabbitMQ_username} ".*" ".*" ".*"

.. note:: 3.1.4 インストール設定ファイルの編集にて記述頂きました、ユーザ名/パスワードでユーザ作成してください。

| 8.2 MariaDB
| Exastro OASE 用のデータベース、ユーザ作成を実施するため、以下のコマンドを実行してください。

| 1 Exastro OASE用のデータベースとユーザ作成

.. code-block:: bash

 # mysql -u root -p{db_root_password}

.. code-block:: bash

 MariaDB [(none)]> CREATE DATABASE {db_name} CHARACTER SET utf8;
 MariaDB [(none)]> CREATE USER '{db_username}' IDENTIFIED BY '{db_password}';
 MariaDB [(none)]> GRANT ALL ON {db_name}.* TO '{db_username}';
 MariaDB [(none)]> quit

.. note:: 3.1.4 インストール設定ファイルの編集にて記述頂きました、rootパスワード、データベース名、ユーザ名、パスワードで作成してください。

.. danger:: 注意

 | Exastro OASE のインストールではインストール済みのソフトウェアはスキップを行います。
 | アップグレードは行いませんのでご注意ください。

1. 注意事項
-------------------------------

4 ディシジョンテーブル作成可能数
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

| ディシジョンマネージャは環境によって作成できるディシジョンテーブル数が変動します。
| ディシジョンテーブルの最大作成可能数はデフォルトでは4ファイル程度となります。
| 記載ルール数またはルール自体の複雑度によってディシジョンテーブル作成数が前後する可能性があります。
| より多くのディシジョンテーブルの作成を実施したい場合はチューニングが必要となります。

.. danger:: 注意

 | ディシジョンテーブルの最大作成数を超えた場合、ディシジョンテーブルのアップロード・プロダクション適用に失敗する可能性があります。
 | 失敗した場合、以下のディレクトリのログを確認してください。
 | RHDMの場合
 | /var/log/jboss-eap/console.log
 | droolsの場合
 | [JBossのインストールディレクトリ]/wildfly-x.x.x.Final/standalone/log/server.log
 | OutOfMemoryErrorの障害が発生している場合は再起動コマンドを実行してください。
 | RHDMの場合
 | # systemctl restart jboss-eap-rhel.service
 | droolsの場合
 | # systemctl restart drools.service
 | 再起動後、以下のコマンドを実行して、KIEコンテナーの一覧を確認します。
 | # curl -u [ルールエンジン管理ユーザー名]:[ルールエンジン管理パスワード] -H "accept: application/json" -X GET "http://[IPアドレス]:8080/decision-central/rest/controller/management/servers"
 | 削除したいKIEコンテナーのcontainer-idを指定して以下のコマンドを実行することにより、KIEコンテナーが削除されます。
 | # curl -u [ルールエンジン管理ユーザー名]:[ルールエンジン管理パスワード] -X DELETE "http://[IPアドレス]:8080/decision-central/rest/controller/management/servers/default-kieserver/containers/[container-id]" -H "accept: application/json"
 | ※IPアドレスはルールエンジンをインストールしたサーバのアドレス
 |
 | ※ルールエンジンを変更した場合、変更前のルールは移行されず、アンインストール時に削除されます。

.. note::

 | より多くのディシジョンテーブルの作成を実施したい場合はJBOSSヒープサイズのチューニングを行う必要があります。
 | チューニング方法は下記の通りです。
 | RHDMの場合
 | # systemctl stop jboss-eap-rhel.service
 | # vi {jboss_root_directory}/bin/standalone.conf
 | 以下の行のサイズを修正する。
 | JAVA_OPTS="-Xms64m -Xmx1024m -XX:MetaspaceSize=96M -XX:MaxMetaspaceSize=1024m -Djava.net.preferIPv4Stack=true"
 | # systemctl start jboss-eap-rhel.service
 | droolsの場合
 | # systemctl stop drools.service
 | # vi {jboss_root_directory}/wildfly-14.0.1.Final/bin/standalone.conf
 | 以下の行のサイズを修正する。
 | JAVA_OPTS="-Xms64m -Xmx1024m -XX:MetaspaceSize=96M -XX:MaxMetaspaceSize=1024m -Djava.net.preferIPv4Stack=true"
 | # systemctl start drools.service
 | ※{jboss_root_directory}はoase_answers.txtのjboss_root_directory項目に記述したディレクトリパスに置換してください。
