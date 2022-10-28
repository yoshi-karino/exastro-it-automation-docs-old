=========================
アンインストール ※準備中
=========================

| Exastro OASE のアンインストール手順について説明します。
| よくあるユースケースに従って、4つのアンインストール方法を紹介します。


前提条件
========

 インストール時の設定値が必要となりますので、インストール設定ファイルが必要になります。


方法1: データを残す場合
============================

install_mode
  | **Uninstall** : アンインストールを指定します。

db_root_password
  | MariaDB の root パスワードを指定します。

db_erase
  | **leave** : アンインストール時に MariaDB からデータを削除しません。

oase_directory
  | **<Exastro OASE のインストール先のディレクトリ>/OASE** を指定します。 


方法2: データを削除する場合
============================

 install_mode
  | **Uninstall** : アンインストールを指定します。

 db_root_password
  | MariaDB の root パスワードを指定します。

 db_erase
  | **erase** : アンインストール時に MariaDB からデータを削除します。

 oase_directory
  | **<Exastro OASE のインストール先のディレクトリ>** を指定します。 


インストーラ実行
================

.. tip::
   | 各プロセスのインストール先のディレクトリを下記のようにしております。
   | Exastro OASE: **/exastro**
   | JBoss (WildFly): **/exastro/JBoss**

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
   | **<extract_path>/oase/oase_install_package/install_scripts/logs**
   | 本マニュアルの手順では、下記となります。
   | **/tmp/oase/oase_install_package/install_scripts/logs**


| インストーラ実行結果を確認します。
| 標準出力、または、インストールログに下記のように表示された場合はインストールが正常に完了しております。

.. code-block:: text

   [2020-11-12 08:59:43] INFO : Finished to install
   [2020-11-12 08:59:43] #####################################
   [2020-11-12 08:59:43] INFO : Install Finished
   [2020-11-12 08:59:43] #####################################
