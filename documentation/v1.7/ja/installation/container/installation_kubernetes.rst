==========
Kubernetes
==========

| Kubernetes を利用した Docker 版 Exastro OASE の導入方法について説明します。
| 非コンテナ環境における導入の場合には、:doc:`../installer/installation_online` か :doc:`../installer/installation_offline` を参照して下さい。


前提条件
========
* Kubernetes 環境が必要となります。
* kubectl コマンドが必要となります。
* git コマンドが必要となります。


コンテナ起動(簡易版)
====================

| kubectl コマンドを使い GitHub にある Kubernetes マニフェストファイルをそのまま利用する方法について説明します。
| 簡単にデプロイできる一方で、データの永続化に hostPath を利用しているため、可用性や保守性が低下します。

永続データ用のディレクトリ作成
------------------------------

| 永続データを格納するためのディレクトリを作成します。

.. code-block:: bash

   # ボリューム作成(ワーカーノードで実施)
   mkdir -p /tmp/oase/{business-central/data,logs,mariadb/data,rabbitmq/data,share}
   chmod -R 777 /tmp/oase

デプロイ
--------

| Kubernetes クラスタ上に Exastro OASE をデプロイします。

.. code-block:: bash

    kubectl apply -f https://raw.githubusercontent.com/exastro-suite/oase-container/main/kubernetes.yaml


コンテナ起動(カスタム版)
========================

| GitHub 上にある Kubernetes マニフェストを `kustomize <https://kustomize.io/>`_ を利用してユーザ環境に合わせてデプロイする方法を紹介します。
| 環境に合わせたストレージやネットワークの設定ができる一方で、ストレージの調達などの事前の準備が必要となります。

Kubernetes マニフェストの取得
-----------------------------

| GitHub から Kubernetes マニフェストを取得します。

.. code-block:: bash

   git clone https://github.com/exastro-suite/oase-container.git

設定ファイルの更新
------------------

| 環境に合わせてマニフェストファイルを修正します。
| kustomize を利用する際には、 :file:`oase-container/kubernetes/overlays` 配下に :file:`kustomization.yaml` を配置します。

カスタム版のマニフェストファイルの適用
--------------------------------------

| Kustomize を使いカスタム版のマニフェストファイルを Kubernetes クラスタに適用します。

.. code-block:: bash

    cd oase-container
    kubectl apply -k kubernetes/overlays


接続確認
========

.. include:: ../../include/confirm_login.rst


環境情報
========

環境変数
--------

.. csv-table::
   :header: 設定名, 初期値, 説明
   :widths: 16,     25,   25

      DB_ROOT_PASSWORD, Ch@ngeMe, MariaDB の root パスワードを指定します。
      DB_HOST, mariadb, Exastro OASE が利用する MariaDB のFQDN(IPアドレス)を指定します。
      DB_PORT, 3306, Exastro OASE が利用する MariaDB の接続ポートを指定します。
      DB_DATABASE, OASE_DB, Exastro OASE が利用する MariaDB のデータベース名を指定します。
      DB_USER, OASE_USER, Exastro OASE が利用する MariaDB のユーザ名を指定します。
      DB_PASSWORD, Ch@ngeMe, Exastro OASE が利用する MariaDB のユーザのパスワードを指定します。
      BUSINESS_CENTRAL_ENDPOINT, central:8080, Exastro OASE が利用する Business Central のエンドポイント+ポート番号を指定します。
      KIE_SERVER_ENDPOINT, server:8080, Exastro OASE が利用する KIE サーバのエンドポイント+ポート番号を指定します。
      JBOSS_USER, admin, Exastro OASE が利用する Business Central のユーザ名を指定します。
      JBOSS_PASSWORD, admin, Exastro OASE が利用する Business Central のユーザのパスワードを指定します。
      MQ_HOST, rabbitmq, Exastro OASE が利用する RabbitMQ のをFQDN(IPアドレス)を指定します。
      MQ_USER, admin, Exastro OASE が利用する RabbitMQ のユーザ名を指定します。
      MQ_PASSWORD, Ch@ngeMe, Exastro OASE が利用する RabbitMQ のユーザのパスワードを指定します。
      MAIL_SMTP, {}, Exastro OASE が連携するメールサーバの情報を設定します。
      INTERVAL_TIME_<ANY>, 10, バックヤード系処理の処理間隔
      RABBITMQ_DEFAULT_USER, admin, RabbitMQ のユーザ名を設定します。
      RABBITMQ_DEFAULT_PASS, Ch@ngeMe, RabbitMQ のユーザのパスワードを設定します。
      MARIADB_ROOT_PASSWORD, Ch@ngeMe, MariaDB の root パスワードを設定します。
      MARIADB_DATABASE, OASE_DB, データベースの名前を設定します。
      MARIADB_USER, OASE_USER, データベースに接続するユーザ名を設定します。
      MARIADB_PASSWORD, Ch@ngeMe, データベースに接続するユーザのパスワードを設定します。
      MARIADB_ROOT_HOST, "%", MariaDB に root ログイン可能なホストを設定します。
      KIE_SERVER_LOCATION, http://kie-server:8080/kie-server/services/rest/server, KIE サーバのエンドポイントを指定します。
      KIE_SERVER_CONTROLLER, http://business-central:8080/business-central/rest/controller, KIE サーバコントローラのエンドポイントを指定します。
      KIE_MAVEN_REPO, http://business-central:8080/business-central/maven2, Maven リポジトリのエンドポイントを指定します。

コンフィグファイル設定
----------------------

なし

