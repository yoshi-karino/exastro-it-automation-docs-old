========================
アクションドライバの作成
========================

| 新規アクションドライバの作成方法についてITA(Exastro IT Automation)アクションドライバの導入を例に説明します。
| Exastro OASE におけるアクションドライバとは、自動対処のためのソフトウェアと連携するための機能を指します。

.. note::
   | **Exastro IT Automation** のことを省略して **ITA** と記載する場合があります。

ITA(Exastro IT Automation)アクションドライバの追加
==================================================

| アクションドライバの設定は、画面上部のメニューの :menuselection:`システム --> アクション設定` から行います。
| 新たにアクションドライバを登録するために、:guilabel:` アクション先の追加` をクリックします。

|  :menuselection:`アクション先の追加`  設定フォームから設定を行います。

.. figure:: /images/ja/quickstart/new_action_driver_01.png
   :width: 400px
   :align: left

   アクション先の追加

アクション先の選択
   | 連携ソフトウェア(ITA)に対応するアクションドライバを選択します。
   |  :program:`ITA Driver ver1`  を選択します。

.. raw:: html

   <div style="clear:both;"></div>

|  :menuselection:`ITA Driver ver1`  設定フォームで、連携する連携ソフトウェア(ITA)に対する接続情報とディシジョンテーブル連携のための設定を行います。

.. figure:: /images/ja/quickstart/new_action_driver_02.png
   :width: 400px
   :align: left

   ITA Driver ver1

名前
   | アクションドライバ名を入力します。
   | クイックスタートでは :program:`新規ITAアクションドライバ` として登録します。

バージョン
   | 連携ソフトウェア(ITA)のバージョンを選択します。

プロトコル
   | 連携ソフトウェア(ITA)との接続のための通信プロトコルを選択します。
   | クイックスタートでは :program:`http` を選択します。

ホスト/IP
   | 連携ソフトウェア(ITA)に接続するためのホスト名、もしくは、IPアドレスを指定します。

ポート
   | 連携ソフトウェア(ITA)と接続時に使用するポート番号を指定します。
   | クイックスタートでは :program:`80` 番ポートを使用します。

ユーザ名
   | 連携ソフトウェア(ITA)にログインで使用するユーザを入力します。

   .. warning::
      | Exastro OASE のロールに紐づくITAユーザを指定する必要があります。

パスワード
   | 連携ソフトウェア(ITA)にログインするためのパスワードを入力します。

権限の設定
   | グループに割り当てる権限を定義します。
   | 全項目を更新可能に設定します。

.. raw:: html

   <div style="clear:both;"></div>


| 全ての項目の入力が完了したら、:guilabel:` 保存` をクリックします。
| 新規に追加したアクションドライバが一覧画面に表示されます。

.. figure:: /images/ja/quickstart/new_action_driver_03.png
   :width: 800px
   :align: center

   アクションドライバ一覧
