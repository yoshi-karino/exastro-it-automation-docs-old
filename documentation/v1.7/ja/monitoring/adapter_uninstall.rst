==============================
監視アダプタのアンインストール
==============================

| 本章では、Exastro OASE がインストール済みの環境で、監視アダプタを削除する場合の方法について説明します。
| 既に、利用したい監視アダプタが未導入の場合は、本手順は不要です。
| また、本手順はインストーラ版(非コンテナ版)を利用している場合の手順となります。

監視アダプタのアンインストール
==============================

| アンインストール対象の監視アダプタをアンインストールする際には、下記の監視アダプタIDをオプションで指定する必要があります。

.. csv-table:: 監視アダプタID
   :header: 監視アダプタID,監視アダプタ,バージョン
   :widths: 20, 40, 30

   1, Zabbixアダプタ, v1
   2, Prometheusアダプタ, v1
   3, Grafanaアダプタ, v1
   4, Datadogアダプタ, v1
   5, メールアダプタ, v1


.. code-block:: bash

   # Exastro OASE のメインプロジェクトのディレクトリに移動
   cd ${INSTALLATION_PATH}/oase/oase-root

   # 監視アダプタのアンインストール
   python3 manage.py adapter_installer -p [pluginsパス] -u [監視アダプタID]

   # 例) Zabbixアダプタアンインストール例
   python3 manage.py adapter_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -u 1

