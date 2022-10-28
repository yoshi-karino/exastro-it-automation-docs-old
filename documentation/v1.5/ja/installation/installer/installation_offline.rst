======================
オフラインインストーラ
======================

| オフラインによる Exastro OASE 導入のための手順について説明します。
| :doc:`../requirements` を確認の上、作業を実施して下さい。

前提条件
========

オフラインインストール時はオフライン環境で実施可能ですが、インストールに必要な資材の収集時にはインターネットに接続できる必要があります。
インストール先の OS とインストール資材収集で利用する OS は一致している必要があります。

| オンライン環境でのインストール方法については :doc:`installation_online` を参考にして下さい。


インストール資材収集
====================



事前準備
========

| インストール時の環境

.. code-block:: bash

    # Exastro OASE v1.5.0 の場合
    OASE_VER="1.5.0"

    # 資材展開先ディレクトリ
    EXTRACT_PATH=/tmp

    # インストール先ディレクトリ
    INSTALLATION_PATH=/exastro

| タイムゾーンの設定

.. code-block:: bash

   # 現在のタイムゾーンを確認
   timedatectl status
   Time zone: <any_time_zone>

   # タイムゾーンを変更する場合
   sudo timedatectl set-timezone <your_time_zone>

   # 日本時間の場合
   sudo timedatectl set-timezone Asia/Tokyo

   # 現在のタイムゾーンを再確認
   timedatectl status
   Time zone: Asia/Tokyo (JST, +0900)

必須パッケージインストール
==========================

| 必須パッケージのインストール

.. code-block:: bash

   sudo yum install -y gcc wget

最新リリース資材の入手
======================

| リリース資材を取得するには、コードを配置するディレクトリに移動して実行します。

.. tip:: | 作業用ディレクトリは今後の手順でも利用します。
         | 本マニュアルでは、資材の展開先(EXTRACT_PATH)を **/tmp** とした想定で説明します。 

| リリース資材のダウンロード

.. code-block:: bash

    # Exastro OASE v1.5.0 の場合
    OASE_VER=1.5.0
    wget -P ${EXTRACT_PATH} https://github.com/exastro-suite/oase/releases/download/v${OASE_VER}/exastro-oase-${OASE_VER}.tar.gz
    
| 資材の展開

.. code-block:: bash

    tar zxvf ${EXTRACT_PATH}/exastro-oase-${OASE_VER}.tar.gz -C ${EXTRACT_PATH}

| (オプション) 展開先の確認
| ※展開後のディレクトリ構成

.. code-block:: bash

    # tree コマンドの取得
    sudo yum -y install tree

    # 展開先の確認
    tree --charset=C ${EXTRACT_PATH}/oase/

    # 出力結果
    /tmp/oase/
    |-- CHANGELOG.md
    |-- LICENSE
    |-- NOTICE
    |-- README_ja.md
    |-- licenses
    |   |-- Django.txt
    |   |-- configparser.txt
    |   |-- djangorestframework.txt
    |   |-- fasteners.txt
    |   |-- jQuery.txt
    |   |-- ldap3.txt
    |   |-- openpyxl.txt
    |   |-- pycrypto.txt
    |   |-- pytz.txt
    |   |-- ress.txt
    |   |-- retry.txt
    |   `-- xlrd.txt
    |-- oase-root
    |   |-- backyards
    |   |   |-- accept_driver
    |   |   |   |-- oase-accept.service
    |   |   |   `-- oase_accept.py
    |   |   |-- action_driver
    |   |   |   |-- oase-action.service
    |   |   |   |-- oase_action.py
    |   |   |   `-- oase_action_sub.py

    ～(略)～

    `-- tool
        |-- conf
        |   |-- Grafana.conf
        |   |-- ITA.conf
        |   |-- Prometheus.conf
        |   |-- ServiceNow.conf
        |   |-- ZABBIX.conf
        |   `-- mail.conf
        |-- encrypter.py
        `-- service
            |-- nginx.service
            `-- uwsgi.service

インストール設定ファイルの作成
==============================


.. tip:: | 本マニュアルでは、資材の展開先(EXTRACT_PATH)を **/tmp** とした想定で説明します。 
         | 資材の展開先が異なる場合、パスを読み替えて下さい。

| 環境構築を行うシェルのあるディレクトリに移動します。

.. code-block:: bash
   
   cd ${EXTRACT_PATH}/oase/oase_install_package/install_scripts


| インストール設定ファイル（oase_answers.txt）を作成します。
| 既存のインストール設定ファイル（oase_answers.txt）は、サンプルとなりますので使用する環境に応じて適宜変更してください。


インストール時の設定各設定項目
------------------------------

| インストール設定ファイルの各設定項目に関しては下記を参照して下さい。

.. include:: ../../include/installation_configuration_online.rst


インストール設定ファイルのサンプル (商用向け)
---------------------------------------------

| 商用向けインストール設定ファイル（oase_answers.txt）のサンプルを以下に示します。
| また、インストール条件は下記となります。

インストール方式
  | オンラインインストール

判断ロジック
  | Red Hat Decision Manager

インストール先OS
  | Red Hat Enterprise Linux 7

.. include:: ../../include/sample_configuration_commercial.rst

インストール設定ファイルのサンプル (非商用向け)
-----------------------------------------------

| 非商用向けのインストール設定ファイル（oase_answers.txt）のサンプルを以下に示します。
| また、インストール条件は下記となります。

インストール方式
  | オンラインインストール

判断ロジック
  | Drools

インストール先OS
  | CentOS 7

.. include:: ../../include/sample_configuration_uncommercial.rst


インストーラ実行
================

.. tip::
   | 各プロセスのインストール先のディレクトリを下記のようにしております。
   | Exastro OASE: :file:`/exastro``
   | JBoss (WildFly): :file:`/exastro/JBoss`

| 環境構築ツールを実行します。

.. code-block:: bash
   
   # root にスイッチ
   sudo su -
   
   # インストーラのあるディレクトリに移動
   cd ${EXTRACT_PATH}/oase/oase_install_package/install_scripts

   # インストーラの実行
   sh oase_installer.sh

.. tip::
   | インストールログは下記に作成されます。
   | :file:`<extract_path>/oase/oase_install_package/install_scripts/logs`
   | 本マニュアルの手順では、下記となります。
   | :file:`/tmp/oase/oase_install_package/install_scripts/logs`


| インストーラ実行結果を確認します。
| 標準出力、または、インストールログに下記のように表示された場合はインストールが正常に完了しております。

.. code-block:: text

   [2020-11-12 08:59:43] INFO : Finished to install
   [2020-11-12 08:59:43] #####################################
   [2020-11-12 08:59:43] INFO : Install Finished
   [2020-11-12 08:59:43] #####################################

Django 設定
===========

| Django の :program:`HOST_NAME` を設定します。
| :program:`HOST_NAME` は、Exastro OASE サーバに接続する際の URL を指定します。

.. code-block:: bash

   # 本書における例
   vi ${INSTALLATION_PATH}/OASE/oase-root/confs/frameworkconfs/settings.py

.. code-block:: python
   
   # オールインワン構成の場合(全てのプロセスが同一サーバ上で起動する場合)
   HOST_NAME = 'https://127.0.0.1'

   # 例) ドメイン名で指定する場合
   HOST_NAME = 'https://oase.example.com:8080'

| その他の設定値については、プロジェクトの環境に応じて適宜変更をして下さい。
| 設定を反映するために、Web サービスを再起動します。

.. code-block:: bash

   systemctl restart httpd

接続確認
========

.. include:: ../../include/confirm_login.rst
