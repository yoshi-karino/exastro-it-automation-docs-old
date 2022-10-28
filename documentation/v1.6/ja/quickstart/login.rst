========
ログイン
========

| Exastro OASE のインストール完了直後の初回ログイン方法と初期パスワードの変更方法について説明します。
| ログイン画面では、OASE を利用して作業を行う上で共通に必要となる以下の機能を提供します。

初回ログイン
============

| OASE の画面にアクセスした場合、ログイン画面の各入力項目に値を入力します。

.. figure:: /images/ja/quickstart/login_form.png
   :scale: 30%
   :align: left
   :alt: "パスワード入力フォーム"

   パスワード入力フォーム

.. csv-table:: 初回ログイン時の入力内容
   :header: 入力項目, 入力値, 説明
   :widths: 15, 15, 30

   Login ID, :kbd:`administrator`, システム管理者のログインIDを入力します。
   Password, :kbd:`oaseoaseoase`, システム管理者のログインパスワードを入力します。

.. raw:: html

   <div style="clear:both;"></div>

|  :guilabel:` Login` ボタンを押下します。


.. _change-pw:

初期パスワード変更
==================

| 初回ログイン時は、初期パスワードの変更の必要があります。
| 現在のパスワードと。新しいパスワードを入力します。

.. figure:: /images/ja/quickstart/init_password01.png
   :scale: 30%
   :align: left
   :alt: "パスワード変更フォーム"

   パスワード変更フォーム

.. csv-table:: パスワード変更時の入力内容
   :header: 入力項目, 入力値, 説明
   :widths: 15, 15, 30

   既存のパスワード, :kbd:`oaseoaseoase`, システム管理者の初期パスワードを入力します。
   既存のパスワード, 新しいパスワード, パスワードの入力条件に従って、新しいパスワードを入力します。
   新規のパスワードの再入力, 新しいパスワード, 入力したパスワードが正しいかの確認のため、もう一度パスワードを入力します。


.. note:: | パスワードは下記の条件を満たす必要があります。
          | ・8文字以上、64文字以下
          | ・半角英数(大文字)、半角英数(小文字)、半角数字、記号を全てを含む

.. raw:: html

   <div style="clear:both;"></div>

|  :guilabel:` 変更する` ボタンを押下します。

.. figure:: /images/ja/quickstart/init_password02.png
   :scale: 30%
   :align: left
   :alt: "パスワード変更確認ダイアログ"

   パスワード変更確認ダイアログ

.. raw:: html

   <div style="clear:both;"></div>

| :guilabel:`OK` ボタンを押下すると、パスワードが変更され、ログアウトされます。


変更後のパスワードでログイン
============================

:ref:`初期パスワード変更 <change-pw>` で設定したパスワードを使い、再度ログインをします。

.. figure:: /images/ja/login/main02.png
   :scale: 30%
   :align: left
   :alt: "ログイン画面"

   ログイン画面

.. csv-table:: ログイン時入力内容
   :header: No., 入力項目, 入力値, 説明
   :widths: 2, 15, 15, 30

   ①, Login ID, administrator, システム管理者のログインIDを入力します。
   ②, Password, :ref:`初期パスワード変更 <change-pw>` で設定したパスワード, システム管理者のログインパスワードを入力します。

.. raw:: html

   <div style="clear:both;"></div>

| :guilabel:` Login` をクリックすると、下記のようにダッシュボードが表示されます。

.. figure:: /images/ja/dashboard/dashboard_no_data.png
   :width: 80%
   :align: center

   初回ログイン時ダッシュボード

.. raw:: html

   <div style="clear:both;"></div>
