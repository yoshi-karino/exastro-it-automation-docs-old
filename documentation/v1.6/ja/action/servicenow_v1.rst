===================
ServiceNow ドライバ
===================

| ServiceNow ドライバは、ServiceNow に対してワークフローの実行やインシデント管理、承認フローを実施するための仕組みです。
| ディシジョンテーブルに対して、複数の ServiceNow アカウントと連携することが可能です。

新規登録
========

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開きます。
| 画面上部にある、:guilabel:` アクション先の追加` ボタンを押下します。
| 「ServiceNow Driver ver1」を選択します。

.. tip::
    | アクション設定を追加するために、アクション設定に対する「更新可能」のアクセス権限が必要です。


.. figure:: /images/ja/action/action_06.png
   :scale: 80%
   :align: center

   アクション設定の選択

| ServiceNow ドライバの設定項目を入力します。

.. figure:: /images/ja/action/action_52.png
   :scale: 35%
   :align: left

   ServiceNow ドライバ(ver. 1)設定画面


.. csv-table:: ServiceNow ドライバ(ver. 1)設定項目
   :header: 設定項目, 説明
   :widths: 20, 60

   名前, Exastro OASEで管理する連携ソフトウェアの名前を設定してください。
   プロトコル, 連携先の ServiceNow インスタンスとの通信プロトコルを「http」または「https」から選択します。
   ホスト/IP, 連携先の ServiceNow インスタンスの FQDN もしくはおよびIPアドレスを入力できます。
   ポート, 連携先の ServiceNow インスタンスとの通信に用いるポート番号を入力します。
   ユーザ名, ServiceNow アカウントのユーザ名を入力します。
   パスワード, ServiceNow アカウントのユーザに紐づくパスワードを入力します。
   プロキシ, インターネット接続のために必要なプロキシサーバの接続先を入力します。(任意)

.. raw:: html

   <div style="clear:both;"></div>

| 各項目の入力が完了したら、:guilabel:` 保存` ボタンを押し設定を保存します。

設定変更
========

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開き、 :menuselection:`ServiceNow Driver ver1` タブを押下し、ServiceNow ドライバの一覧を表示します。

.. figure:: /images/ja/action/action_53.png
   :scale: 60%
   :align: center

   ServiceNow ドライバ一覧

| 編集対象のアクション設定の詳細確認ボタン :guilabel:`` をクリックし、詳細画面を開きます。

.. figure:: /images/ja/action/action_54.png
   :scale: 60%
   :align: center

   ServiceNow ドライバ詳細画面

| 画面下部にある :guilabel:` 編集` ボタンから編集画面を開き、該当の項目を編集します。

.. figure:: /images/ja/action/action_55.png
   :scale: 60%
   :align: center

   ServiceNow ドライバ編集画面

| 各項目の入力が完了したら、:guilabel:` 保存` ボタンを押し設定を保存します。