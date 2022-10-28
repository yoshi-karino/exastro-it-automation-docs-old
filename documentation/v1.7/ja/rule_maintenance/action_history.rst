==============
アクション履歴
==============

| アクション履歴画面では、アクションの状況や結果を確認するだけではなく、承認待ちで一時停止状態となっているアクションの承認や却下を行うことができます。

| OASE アクション履歴画面の画面構成と、各構成要素について説明します。


アクション履歴確認
==================

| イベントが発生しルールにマッチした場合、アクションが実行されます。
| 実行されたアクションを確認するために、 :menuselection:`ルール --> アクション履歴` メニューから :menuselection:`アクション履歴` 画面を開きます。

.. figure:: /images/ja/action_history/action_history_01.png
   :scale: 80%
   :align: center

   アクション履歴画面

.. warning:: 
   | アクション履歴を表示するために、該当のディシジョンテーブルに対して「参照のみ」もしくは「更新可能」の権限が必要となります。

| 各アクションの状態を示すのアイコンの意味は次のとおりです。

.. list-table:: ステータスアイコン
    :widths: 20, 60
    :header-rows: 1

    * - アイコン
      - 説明
    * - .. figure:: /images/ja/action_history/check.png
           :scale: 20%
      - アクション正常終了の時に表示されるステータスアイコンです。
    * - .. figure:: /images/ja/action_history/gear.png
           :scale: 20%
      - アクション実行中に表示されるステータスアイコンです。
    * - .. figure:: /images/ja/action_history/cross.png
           :scale: 20%
      - アクション強制終了の時に表示されるステータスアイコンです。
    * - .. figure:: /images/ja/action_history/stop.png
           :scale: 20%
      - アクション承認待ちの時に表示されるステータスアイコンです。
    * - .. figure:: /images/ja/action_history/square.png
           :scale: 20%
      - アクション承認待ちキャンセル時に表示されるステータスアイコンです。
    * - .. figure:: /images/ja/action_history/attention.png
           :scale: 20%
      - Exastro実行時でエラーになった時に表示されるステータスアイコンです。
    * - .. figure:: /images/ja/action_history/prevent.png
           :scale: 39%
      - アクション抑止済の時に表示されるステータスアイコンです。


アクション実行状況の確認
========================

| 各アクションの実行状況については、詳細表示ボタン :guilabel:`` を押下することで実行状況や実行ログを確認することができます。
| アクション履歴詳細画面は、「リクエスト情報」と「アクション情報」、「ログ」の3つに分かれています。
| また、「アクション情報」はアクション種別により表示される情報が異なります。

.. figure:: /images/ja/action_history/action_history_04.png
   :scale: 60%
   :align: center

   アクション履歴詳細画面

.. csv-table:: アクション履歴詳細の説明
   :header: 項目, 説明
   :widths: 20, 60

   イベント発生日時,アクションが実行される起因となった、イベントの発生日時を表示します。
   イベントシリアルNo.,リクエスト情報の識別子です。
   イベント情報,リクエストされてきたイベント情報を表示します。
   アクション日時,アクション実行日時を表示します。
   イベントシリアルNo.,アクション情報の識別子です。項目2と同じ値が付与されます。
   ディシジョンテーブル名,アクション実行されたディシジョンテーブル名を表示します。
   ルール名,アクション実行されたルール名を表示します。
   発生事象,アクション実行された発生事象が表示されます。
   対処概要,アクション実行された対処概要が表示されます。
   アクションパラメータ情報,アクションを行ったパラメータ情報を表示します。
   ログ情報,アクション実行のログを表示します。出力されるログにはメッセージIDが付与されています。


Exastro IT Automation 実行結果
------------------------------

| 履歴詳細画面における、Exastro IT Automation 固有の実行結果は次の通りです。

* Symphony 実行時

.. figure:: /images/ja/action_history/action_history_12.png
   :scale: 30%
   :align: left

   Symphony 実行結果

.. csv-table:: 固有項目(ITA Symphony実行の場合)の説明
   :header: 構成要素, 説明
   :widths: 20, 60

   ITA表示名,ディシジョンテーブルファイルに記載した、ITA_NAMEが表示されます。
   Symphonyインスタンス番号,ITAで実行されたSymphony作業一覧のIDが表示されます。
   SymphonyクラスID,ITAで実行されたSymphonyクラス一覧のIDが表示されます。
   オペレーションID,ITAで実行された投入オペレーション一覧のIDが表示されます。
   Symphony作業確認URL,ITAの実行結果参照用の、Symphony作業確認のURLが表示されます。
   RESTAPI異常時の詳細内容,OASE-ITA間のREST結果が異常であった場合、エラー内容が表示されます。
   連携項目,メニューID指定によるITAアクションを実施した際に、ITA側に連携した値が表示されます。

.. raw:: html

   <div style="clear:both;"></div>

* Conductor 実行時

.. figure:: /images/ja/action_history/action_history_14.png
   :scale: 30%
   :align: left

   Conductor 実行結果
   

.. csv-table:: 固有項目(ITA Conductor実行の場合)の説明
   :header: 構成要素, 説明
   :widths: 20, 60

   ITA表示名,ディシジョンテーブルファイルに記載した、ITA_NAMEが表示されます。
   Conductorインスタンス番号,ITAで実行されたConductor作業一覧のIDが表示されます。
   ConductorクラスID,ITAで実行されたConductorクラス一覧のIDが表示されます。
   オペレーションID,ITAで実行された投入オペレーション一覧のIDが表示されます。
   Conductor作業確認URL,ITAの実行結果参照用の、Conductor作業確認のURLが表示されます。
   RESTAPI異常時の詳細内容,OASE-ITA間のREST結果が異常であった場合、エラー内容が表示されます。
   連携項目,メニューID指定によるITAアクションを実施した際に、ITA側に連携した値が表示されます。

.. raw:: html

   <div style="clear:both;"></div>

メール送信結果
--------------

.. figure:: /images/ja/action_history/action_history_13.png
   :scale: 30%
   :align: left

   メール送信固有の項目

.. csv-table:: 固有項目(メール送信)の説明
   :header: 構成要素, 説明
   :widths: 20, 60

   メールテンプレート名,アクション実行により送信されたメールテンプレート名が表示されます。
   送信先メールアドレス,アクション実行により送信されたメールアドレスが表示されます。

.. raw:: html

   <div style="clear:both;"></div>

.. note::
    送信先メールアドレスはディシジョンテーブルファイルに記入したメールアドレスか、
    メールテンプレートで記入したメールアドレスか、わかるように表示しています。


ServiceNow 連携結果
-------------------

.. figure:: /images/ja/action_history/action_history_15.png
   :scale: 30%
   :align: left

   ServiceNow 連携の固有項目

.. csv-table:: 固有項目(ServiceNow連携)の説明
   :header: 構成要素, 説明
   :widths: 20, 60

   ServiceNow表示名, ディシジョンテーブルファイルに記載した、SERVICENOW_NAMEが表示されます。
   sys_id, ServiceNow側で付与された、インシデントやワークフローのIDが表示されます。
   Short Description, ServiceNowへ連携した、Short Descriptionが表示されます。


.. raw:: html

   <div style="clear:both;"></div>


アクション履歴詳細の取得
========================

| 詳細情報取得ボタン :guilabel:`` で詳細情報をテキストファイルとして、ダウンロードすることができます。

.. figure:: /images/ja/action_history/action_history_05.png
   :scale: 60%
   :align: center

   アクション履歴詳細の取得


アクション再実行
================
| 実行エラーとなったアクションが再実行可能な場合、再実行ボタン :guilabel:`` を押下することで、再度アクションを実行することができます。

.. figure:: /images/ja/action_history/action_history_07.png
   :scale: 60%
   :align: center

   アクション再実行

.. note::
   | アクションの再実行は該当のディシジョンテーブルに対して「更新可能」の権限が必要となります。


作業承認
========

* ディシジョンテーブルファイルのアクション実行前パラメータ情報を記述したルールがアクションされた際、アクション実行を保留中にすることができます。
* アクション履歴画面の承認・却下ボタンから、アクション実行を行うか、実行せずに停止させるかを選択することができます。

.. include:: ../include/approval_dialog.rst


