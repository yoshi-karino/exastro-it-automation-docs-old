==============
アクション承認
==============

| Exastro OASE が、自動でアクションを行う際に事前にユーザの承認を求めることができます。
| 本項では、承認リクエストを送信する際の :menuselection:`承認メールパラメータ` の記載方法と、承認方法について説明します。

承認リクエスト送信
==================

| メール承認する際に利用する承認メールパラメータについて記載します。
| 基本的には、メール連携時のアクションパラメータと同じ記載となります。

.. note::
   | 承認したいアクションと同じ行にある承認パラメータ情報に記載する必要があります。

.. include:: ../include/mail_action.rst



ユースケース
------------

| **Case 1**
| 特定のユーザに対して承認依頼メールを送信する。

::

 MAIL_NAME=management-mail,MAIL_TO=maintener@example.com,MAIL_CC=dev-team@example.com,MAIL_BCC=

| **Case 2**
| 特定のユーザに対してテンプレートを利用した承認依頼メールを送信する。

::

 MAIL_NAME=management-mail,MAIL_TO=,MAIL_CC=dev-team@example.com,MAIL_BCC=,MAIL_TEMPLATE=request_approval


作業承認
========

| 作業承認を行う場合には、:menuselection:`ルール --> アクション履歴` メニューから :menuselection:`アクション履歴` 画面を開きます。

.. include:: ../include/approval_dialog.rst