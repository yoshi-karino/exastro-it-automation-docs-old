
| Django フレームワークの設定により IP ブロック機能を一時的に無効にした状態で、ホワイトリストに接続元の IP アドレスを追加します。

.. warning::
   | 本作業中は、IPブロックによるアクセス制限機能が一時的に無効の状態になります。

| Django フレームワークの設定ファイルを下記の様に編集し、IP ブロック機能を無効化します。

| Django フレームワークの設定ファイル: :file:`<OASE_DIRECTORY>/OASE/oase-root/confs/frameworkconfs/settings.py`

.. tip::
   | :file:`<OASE_DIRECTORY>` は、インストール時に指定した Exastro OASE のインストール先のディレクトリです。
   | デフォルトでは、 :file:`/exastro/OASE/oase-root/confs/frameworkconfs/settings.py` となります。

.. code-block:: python

   # IP ブロック機能を無効化
   # DISABLE_WHITE_BLACK_LIST = Flase
   DISABLE_WHITE_BLACK_LIST = True


| 設定を反映するために、Apache を再起動します。

.. code-block:: bash

   systemctl restart httpd

| ホワイトリストの :ref:`whitelist_manual` に従い、アクセス元の IP アドレスをホワイトリストに追加します。

| 再度、設定ファイルを下記の様に編集し、IP ブロック機能を有効化します。

.. code-block:: python

   # IP ブロック機能を再度有効化
   DISABLE_WHITE_BLACK_LIST = False

| 設定を反映するために、Apache を再起動します。

.. code-block:: bash

   systemctl restart httpd
