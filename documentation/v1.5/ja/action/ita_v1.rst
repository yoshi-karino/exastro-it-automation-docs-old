===================================
Exastro IT Automation(ITA) ドライバ
===================================

| Exastro IT Automation (以降、ITAとも記載) ドライバは、Exastro IT Automation に対して API を利用して作業指示を行い、またその結果を取得するための仕組みです。
| ディシジョンテーブルに対して、複数の ITA サーバと連携することが可能です。

新規登録
========

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開きます。
| 画面上部にある、:guilabel:` アクション先の追加` ボタンを押下します。
| 「ITA Driver ver1」を選択します。

.. tip::
    | アクション設定を追加するために、アクション設定に対する「更新可能」のアクセス権限が必要です。


.. figure:: /images/ja/action/action_06.png
   :scale: 80%
   :align: center

   アクション設定の選択

| ITA ドライバの設定項目を入力します。

.. figure:: /images/ja/action/action_22.png
   :scale: 35%
   :align: left

   ITA ドライバ(ver. 1)設定画面


.. csv-table:: ITA ドライバ(ver. 1)設定項目
   :header: 設定項目, 説明
   :widths: 20, 60

   名前, Exastro OASEで管理する連携ソフトウェアの名前を設定してください。
   バージョン, 連携先の ITA のバージョンを選択します。
   プロトコル, 連携先の ITA との通信プロトコルを「http」または「https」から選択します。
   ホスト/IP, 連携先の ITA の FQDN もしくはおよびIPアドレスを入力できます。
   ポート, 連携先の ITA との通信に用いるポート番号を入力します。
   ユーザ名, ITA ユーザ名を入力します。
   パスワード, ITA ユーザに紐づくパスワードを入力します。

.. raw:: html

   <div style="clear:both;"></div>

| 各項目の入力が完了したら、:guilabel:` 保存` ボタンを押し設定を保存します。

.. tip:: 
   | **連携するITAツールのバージョンが1.8.1以降の場合:**
   | 登録するユーザは、ITAツール側の管理コンソール - ロール管理にデフォルトで登録されている、oaseアクションロールを紐づけたユーザをご利用ください。

.. warning:: 
   | **連携するITAツールのバージョンが1.8.0以前の場合:**
   | ITAツール側の管理コンソール - ロール・メニュー紐付管理にて以下のメニューを復活させる必要があります。
   | ・ **メニューID:2100160002 メニュー名:メニュー項目作成情報**
   | ・ **メニューID:2100160002 メニュー名:メニュー項目作成情報**

設定変更
========

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開き、 :menuselection:`ITA Driver ver1` タブを押下し、ITA ドライバの一覧を表示します。

.. figure:: /images/ja/action/action_23.png
   :scale: 60%
   :align: center

   ITA ドライバ一覧

| 編集対象のアクション設定の詳細確認ボタン :guilabel:`` をクリックし、詳細画面を開きます。

.. figure:: /images/ja/action/action_24.png
   :scale: 60%
   :align: center

   ITA ドライバ詳細画面

| 画面下部にある :guilabel:` 編集` ボタンから編集画面を開き、該当の項目を編集します。

.. figure:: /images/ja/action/action_25.png
   :scale: 60%
   :align: center

   ITA ドライバ編集画面

| 各項目の入力が完了したら、:guilabel:` 保存` ボタンを押し設定を保存します。