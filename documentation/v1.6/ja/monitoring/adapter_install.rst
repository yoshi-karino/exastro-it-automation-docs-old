==========================
監視アダプタのインストール
==========================

| 本章では、Exastro OASE がインストール済みの環境で、監視アダプタを追加する場合の方法について説明します。
| 既に、利用したい監視アダプタがインストール済みの場合は、本手順は不要です。
| また、本手順はインストーラ版(非コンテナ版)を利用している場合の手順となります。

監視アダプタ資材の展開
======================

| 監視アダプタのリソース自体は Exastro OASE のインストール先に格納されています。
| 監視アダプタのインストールを始める前に、資材を展開します。

.. tip::
   | 各プロセスのインストール先のディレクトリを下記のようにしております。
   | Exastro OASE: **/exastro**
   | JBoss (WildFly): **/exastro/JBoss**

.. code-block:: bash

   # root にスイッチ
   sudo su -
   
   # Exastro OASE のインストール先のディレクトリを変数に格納
   # 例) /exastro にインストールをした場合
   INSTALLATION_PATH=/exastro
   
   # インストーラのあるディレクトリに移動
   cd ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents

   # 各種アダプタ資材の展開
   tar zxf ZABBIX_Adapter.tar.gz
   tar zxf Prometheus_Adapter.tar.gz
   tar zxf Grafana_Adapter.tar.gz
   tar zxf Datadog_Adapter.tar.gz

監視アダプタのインストール
==========================

| インストール対象の監視アダプタをインストールする際には、下記の監視アダプタIDをオプションで指定する必要があります。

.. csv-table:: 監視アダプタID
   :header: 監視アダプタID,監視アダプタ,バージョン
   :widths: 20, 40, 30

   1, Zabbixアダプタ, v1
   2, Prometheusアダプタ, v1
   3, Grafanaアダプタ, v1
   4, Datadogアダプタ, v1


.. code-block:: bash

   # Exastro OASE のメインプロジェクトのディレクトリに移動
   cd ${INSTALLATION_PATH}/oase/oase-root

   # 監視アダプタのインストール
   python3 manage.py adapter_installer -p [pluginsパス] -i [監視アダプタID]

   # 例) Zabbixアダプタインストール例
   python3 manage.py adapter_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -i 1

