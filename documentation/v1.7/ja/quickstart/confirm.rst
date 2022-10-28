================
アクションの確認
================

| Exastro OASE がアラートメッセージを取得した場合の確認方法について説明します。


動作確認手順
============

| アラートメッセージを発生させるのが難しい場合、手動でアラートメッセージを送信することができます。

.. danger::
    | 自動化ソフトウェアと連携している場合、本番システムへの変更作業が実行されます。
    | 対象のディシジョンテーブルの各種設定やアクションドライバの設定情報を確認することを推奨します。

.. code-block:: bash

  curl -X POST -k 'https://<ip_address_or_fqdn>/oase_web/event/event/eventsrequest' \
   -H 'accept: application/json' \
   -H 'Authorization: Bearer <access_token>' \
   -d '{"decisiontable":"新規ディシジョンテーブル","requesttype":"1","eventdatetime":"<current_datetime>","eventinfo":["This is test alert."]}'

| 各パラメータについては下記を参照に適書き換えて下さい。

*ip_address_or_fqdn*
  | Exastro OASE に接続可能な IP アドレスや FQDN を入力します。

*access_token*
  | :doc:`rule` で払い出したトークンを入力します。

*current_datetime*
  | 現在日時を「YYYY/MM/DD HH:mm:ss」形式で入力します。


リクエスト履歴
==============

| 監視アプリケーションからのアラートメッセージ(リクエスト)を取得した場合の確認方法について説明します。
| リクエスト履歴は、画面上部のメニューの :menuselection:`ルール --> リクエスト履歴` から確認します。

.. figure:: /images/ja/quickstart/request_history_01.png
   :width: 800px
   :align: center

   リクエスト履歴

.. note::
  | 取得したリクエストは、全てこの画面に表示されます。


アクション履歴
==============

| 監視アプリケーションからのアラートメッセージ(リクエスト)がディシジョンテーブルに記載したルールにマッチした場合の確認方法について説明します。
| アクション履歴は、画面上部のメニューの :menuselection:`ルール --> アクション履歴` から確認します。

.. figure:: /images/ja/quickstart/action_history_01.png
   :width: 800px
   :align: center

.. note::
  | 取得したリクエストのうち、マッチしたルールに紐づくアクションの全てがこの画面に表示されます。