========
環境設定
========

ログファイルの出力先
====================

日付変更もしくは10MBを超えた場合、ログはローテーションされます。

.. csv-table:: ログファイル
   :header: プロセス名, パス, 保管期間(デフォルト), GUIからの変更
   :widths: 30, 80, 30, 15

   Web App, :file:`{<oase_directory>}/OASE/oase-root/logs/webaplogs/webap.log`, 14日間, 不可
   Agent プロセス, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_agent/oase_agent.log`,  7日間, 可
   Action プロセス, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_action/oase_action.log`, 7日間, 可
   Apply プロセス, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_apply/oase_apply.log`, 7日間, 可
   Accept プロセス, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_accept/oase_accept.log`, 7日間, 可
   Active Directory連携, :file:`{<oase_directory>}/OASE/oase-root/logs/ad_collaboration/ad_collaboration.log`, 7日間, 可
   監視アプリケーション連携, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_monitoring/oase_monitoring.log`, 7日間 ※全アダプター共通設定, 可
   ITA 連携ドライバ, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/exastro_collaboration/exastro_collaboration.log`,14日間, 不可
   ServiceNow 連携ドライバ, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/servicenow_notification/servicenow_notification.log`,14日間, 不可


ステートフルなデータの格納先
============================

.. csv-table:: ステートフルなデータの格納先
   :header: ステートフルなデータ, パス, デフォルト
   :widths: 40, 50, 40

   ディシジョンテーブルファイルの配置先1, :file:`{<rulefile_rootpath>}` ※インストール時に指定, :file:`/exastro/rule`
   ディシジョンテーブルファイルの配置先2, :file:`{<oase_directory>}/OASE/oase-root/temp/rule`, :file:`/exastro/OASE/oase-root/temp/rule`
   セッションファイル, :file:`{<oase_directory>}/OASE/oase-root/temp/sessions`, :file:`/exastro/OASE/oase-root/temp/sessions`
   JBossプロジェクト, :file:`{<jboss_root_directory>}` ※インストール時に指定, :file:`/exastro/JBoss`
   M2リポジトリ, :file:`/root/.m2/repository/com/oase`, :file:`/root/.m2/repository/com/oase`
   MariaDB, :file:`/var/lib/mysql`, :file:`/var/lib/mysql`
   RabbitMQ, :file:`/var/lib/rabbitmq`, :file:`/var/lib/rabbitmq`

.. note::
   | :file:`{<oase_directory>}`、 :file:`{<rulefile_rootpath>}`、および、 :file:`{<jboss_root_directory>}` は、インストール時に指定。