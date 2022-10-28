========
ログ管理
========

| Exastro OASE におけるログの管理について説明します。
| ログ管理では、Exastro OASE の各プロセスが出力するログに対して以下の機能を提供します。

* 保管期間の設定

.. tip::
    | Exastro OASE が連携しているルールエンジン、リレーショナルデータベース、メッセージキューイング機能などの各プロセスのログは管理対象外となります。
    | Exastro OASE の監視アダプタやアクションドライバのログについても管理対象外となります。


ログファイル
============

| ログの出力先については、:doc:`../appendix/environment` を参照して下さい。

ログ保管期間設定
================

| 画面上部のメニューから :menuselection:`システム --> システム設定` を開きます。
| 左メニューから :menuselection:`ログ設定` を選択します。

.. figure:: /images/ja/system_config/logs_column_edit.png
   :scale: 15%
   :align: left

   ログ設定編集画面

.. csv-table:: ログ設定項目
   :header: 設定項目, 説明, 設定値, 初期値
   :widths: 25, 50, 20, 15

   Active Directory連携, Active Directory のログ保存期間。, :kbd:`1 - 7` (日), :kbd:`7` (日)
   oase-agent, Agent プロセスのログ保存期間。, :kbd:`1 - 7` (日), :kbd:`7` (日)
   oase-action, Action プロセスのログ保存期間。, :kbd:`1 - 7` (日), :kbd:`7` (日)
   oase-apply, Apply プロセスのログ保存期間。, :kbd:`1 - 7` (日), :kbd:`7` (日)
   oase-accept, oase-accept プロセスのログ保存期間。, :kbd:`1 - 7` (日), :kbd:`7` (日)

.. raw:: html

   <div style="clear:both;"></div>

| 設定が完了したら :guilabel:` 保存` をクリックします。
| 設定前の状態に戻すには、:guilabel:` リセット` をクリックします。