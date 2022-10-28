==============
マニュアル構成
==============

| 本マニュアルについて説明します。


マニュアルの構成
================

| Exastro Operation Autonomy Support Engine (以降、Exastro OASE と表記)のシステム構築の為のシステム構成や環境構築、運用について説明します。

| :doc:`../introduction/index` では、現在の Exastro OASE に関する一般的な情報を記載しています。
.. * :doc:`../definitions/definitions` では、Exastro OASE で使用する用語を説明しています。
| :doc:`../installation/index` では、Exastro OASE のインストール方法やアップデート方法について記載しています。
| :doc:`../quickstart/index` では、Exastro OASE のログインからルールの作成、そして実際に対処を行うまでの一連の流れを記載しています。
| :doc:`../system/index` では、Exastro OASE で変更可能な設定項目とその内容について記載しています。
| :doc:`../authentication/index` では、ユーザやグループとその権限の設定方法について記載しています。
| :doc:`../security/index` では、Exastro OASE が提供しているセキュリティ機能について記載しています。
| :doc:`../monitoring/index` では、監視アプリケーションとの連携のための設定方法について説明しています。
| :doc:`../action/index` では、対処(アクション)をおこなうためのアプリケーションとの連携のための設定方法について説明しています。
| :doc:`../rule_definition/index` では、監視アプリケーションから取得したアラートメッセージと対処方法を結びつけるルールや対処方法の定義のやり方について記載しています。
| :doc:`../api/index` では、Exastro OASE が提供するシステム関連系のための API について記載しています。
| :doc:`../appendix/index` では、Exastro OASE のシステム内部の情報について記載しています。ユーザが利用する上ではほとんど不要な情報でしょう。


メモ
====

| ユーザが確認すべき内容ごとにレベルが分けをしたメモを記載している箇所がいくつかあります。
| Note や Tip については読み飛ばしてもそれほど運用に影響はありませんが、Warning や Danger は運用上注意が必要な項目となりますので、ユーザが確認することを推奨します。
| 吹き出し形式のメモには下記の意味があります。

.. note:: | 補足的な情報を示しています。
          | Note に記載されている内容は読み飛ばしても困ることは無いでしょう。

.. tip:: | 操作や作業におけるノウハウを示しています。
         | Tip に記載されている内容を読み飛ばした場合ユーザに混乱が生じる可能性があります。

.. warning:: | 操作上の注意点を示しています。
             | Warning に記載された内容はユーザが把握しておくほうが適切な情報です。

.. danger:: | 正常なサービスへ影響を与える可能性がある操作についての危険性を示しています。
            | Danger に記載された内容を知らない場合、大きな問題を引き起こす可能性があります。

表現
====

| 本マニュアルでは、内容に応じて下記のような表現方法を用います。

.. csv-table::  表現例
   :header: 名前, 表現例, 実際の表記(入力例)
   :widths: 20, 20, 60

   menuselection, メニュー・画面・画面内の項目, :menuselection:`メニュー --> サブメニュー`、:menuselection:`画面名`、:menuselection:`項目`
   guilabel, ボタン, :guilabel:`ボタン`
   kbd, キーボード入力, :kbd:`Ctrl + Z`、 :kbd:`入力文字列`
   program, GUI上の設定項目・設定値, :program:`Item`、 :program:`Input data`
   file, ファイル・ディレクトリのパス, :file:`/path/to/file`
   dfn, 用語定義, :dfn:`用語`