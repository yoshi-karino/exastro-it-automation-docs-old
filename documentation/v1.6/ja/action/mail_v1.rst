==============
メールドライバ
==============

| メールドライバは、監視アプリケーションで検知したイベントごとにメール通知を行うための仕組みです。
| ディシジョンテーブルに対して、複数のメールサーバと連携することが可能です。

新規登録
========

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開きます。
| 画面上部にある、:guilabel:` アクション先の追加` ボタンを押下します。
| :menuselection:`mail Driver ver1` を選択します。

.. tip::
    | アクション設定を追加するために、アクション設定に対する「更新可能」のアクセス権限が必要です。


.. figure:: /images/ja/action/action_06.png
   :scale: 80%
   :align: center

   アクション設定の選択

| Mail ドライバの設定項目を入力します。

.. figure:: /images/ja/action/action_09.png
   :scale: 35%
   :align: left

   Mail ドライバ(ver. 1)設定画面


.. csv-table:: Mail ドライバ(ver. 1)設定項目
   :header: 設定項目, 説明
   :widths: 20, 60

   名前, Exastro OASEで管理する連携ソフトウェアの名前を設定してください。
   プロトコル, 連携先のメールサーバとの通信プロトコルを「smtp」または「smtp_auth」から選択します。
   smtpサーバ, 連携先のメールサーバの FQDN もしくはおよびIPアドレスを入力できます。
   ポート, 連携先のメールサーバとの通信に用いるポート番号を入力します。
   ユーザ名, メールアカウントのユーザ名を入力します。
   パスワード, メールアカウントのユーザに紐づくパスワードを入力します。

.. raw:: html

   <div style="clear:both;"></div>

| 各項目の入力が完了したら、:guilabel:` 保存` ボタンを押し設定を保存します。

設定変更
========

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開き、 :menuselection:`Mail Driver ver1` タブを押下し、Mail ドライバの一覧を表示します。

.. figure:: /images/ja/action/action_03.png
   :scale: 60%
   :align: center

   Mail ドライバ一覧

| 編集対象のアクション設定の詳細確認ボタン :guilabel:`` をクリックし、詳細画面を開きます。

.. figure:: /images/ja/action/action_10.png
   :scale: 60%
   :align: center

   Mail ドライバ詳細画面

| 画面下部にある :guilabel:` 編集` ボタンから編集画面を開き、該当の項目を編集します。

.. figure:: /images/ja/action/action_11.png
   :scale: 60%
   :align: center

   Mail ドライバ編集画面

| 各項目の入力が完了したら、:guilabel:` 保存` ボタンを押し設定を保存します。


メールテンプレート
==================

| メールテンプレート機能を使うことで、ルールごとに個別の宛先や件名、本文などでメール通知を行うことができます。

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開きます。
| :menuselection:`mail Driver ver1` タブを選択し、 :guilabel:` メールテンプレート` ボタンを押下します。


.. figure:: /images/ja/action/action_08.png
   :scale: 80%
   :align: center
   
   メールドライバ一覧画面

| :guilabel:` 新規追加` ボタンを押下します。

.. figure:: /images/ja/action/action_40.png
   :scale: 80%
   :align: center
   
   メールテンプレート一覧画面

| メールテンプレートの設定項目を入力します。

.. figure:: /images/ja/action/action_42.png
   :scale: 25%
   :align: left

   メールテンプレート設定画面

.. csv-table:: メールテンプレートの設定項目
   :header: 構成要素, 説明
   :widths: 20, 60

   テンプレート名, テンプレート名を入力します。
   宛先, 送信先のメールアドレスを入力します。
   CC, 送信先のメールアドレスを入力します。
   BCC, 送信先のメールアドレスを入力します。
   件名, メールの件名を入力します。
   本文, メールの本文を入力します。

.. raw:: html

   <div style="clear:both;"></div>

| メールテンプレートの詳細確認や編集を行う場合は、対象のメールテンプレートの詳細確認ボタン :guilabel:`` をクリックし、詳細画面から編集できます。

.. figure:: /images/ja/action/action_45.png
   :scale: 80%
   :align: center

   メールテンプレートの詳細画面

.. tip::
   | メールテンプレートの編集・削除にはアクション設定画面に対する「更新可能」のアクセス権限が必要です。
