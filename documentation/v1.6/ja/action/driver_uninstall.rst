==============================
連携ドライバのアンインストール
==============================

| 本章では、Exastro OASE がインストール済みの環境で、連携ドライバを削除する場合の方法について説明します。
| 既に、利用したい連携ドライバが未導入の場合は、本手順は不要です。
| また、本手順はインストーラ版(非コンテナ版)を利用している場合の手順となります。

連携ドライバのアンインストール
==============================

| アンインストール対象の連携ドライバをアンインストールする際には、下記の連携ドライバIDをオプションで指定する必要があります。

.. csv-table:: 連携ドライバID
   :header: 連携ドライバID,連携ドライバ,バージョン
   :widths: 20, 40, 30

   1, ITA ドライバ, v1
   2, メールドライバ, v1
   3, ServiceNow ドライバ, v1


.. code-block:: bash

   # Exastro OASE のメインプロジェクトのディレクトリに移動
   cd ${INSTALLATION_PATH}/oase/oase-root

   # 連携ドライバのアンインストール
   python3 manage.py driver_installer -p [pluginsパス] -u [連携ドライバID]

   # 例) Zabbixアダプタアンインストール例
   python3 manage.py driver_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -u 1

