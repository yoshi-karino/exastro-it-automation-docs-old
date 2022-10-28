==========================
連携ドライバのインストール
==========================

| 本章では、Exastro OASE がインストール済みの環境で、連携ドライバを追加する場合の方法について説明します。
| 既に、利用したい連携ドライバがインストール済みの場合は、本手順は不要です。
| また、本手順はインストーラ版(非コンテナ版)を利用している場合の手順となります。

連携ドライバ資材の展開
======================

| 連携ドライバのリソース自体は Exastro OASE のインストール先に格納されています。
| 連携ドライバのインストールを始める前に、資材を展開します。

.. tip::
   | 各プロセスのインストール先のディレクトリを下記のようにしております。
   | Exastro OASE: **/exastro**
   | JBoss (WildFly): **/exastro/JBoss**

.. code-block:: bash

   # root にスイッチ
   sudo su -
   
   # Exastro OASE のインストール先のディレクトリを変数に格納
   #../../exastro にインストールをした場合
   INSTALLATION_PATH=/exastro
   
   # インストーラのあるディレクトリに移動
   cd ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents

   # 各種ドライバ資材の展開

   tar zxf ITA_Driver.tar.gz
   tar zxf mail_Driver.tar.gz
   tar zxf ServiceNow_Driver.tar.gz

連携ドライバのインストール
==========================

| インストール対象の連携ドライバをインストールする際には、下記の連携ドライバIDをオプションで指定する必要があります。

.. csv-table:: 連携ドライバID
   :header: 連携ドライバID,連携ドライバ,バージョン
   :widths: 20, 40, 30

   1, ITA ドライバ, v1
   2, メールドライバ, v1
   3, ServiceNow ドライバ, v1


.. code-block:: bash

   # Exastro OASE のメインプロジェクトのディレクトリに移動
   cd ${INSTALLATION_PATH}/oase/oase-root

   # 連携ドライバのインストール
   python3 manage.py driver_installer -p [pluginsパス] -i [連携ドライバID]

   # 例) Zabbixアダプタインストール例
   python3 manage.py driver_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -i 1

