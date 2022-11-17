==============
マニュアル構文
==============

index.rst
=========

役割1
-----

| ビルド時、システムはドキュメントルート、、大章ディレクトリの配下に置かれたindex.rst の内容を見て章と章を紐づけ、全体を構成します。
.. figure:: ../../images/ja_manual_design/role_of_index_rst_v2_0.png
   :width: 5.84375in
   :height: 1.09375in
   :align: center
   :alt: role_of_index

   index.rstの役割

役割2
-----

| 各 index.rst にて見出しを定義します。
|
|各index.rst 内見出

.. code-block:: bash

  documentation
  　|-- html
  　|-- images
  　|-- v2.0
  　|   |-- ja_manual_design
  　|   |   |-- index.rst <-- "マニュアル構成法" を記述
  　|   |
  　|   |-- ja
  　|   |   |-- index.rst <--- "Exastro-it-automation 2.0 操作マニュアル" を記述
  　|   |
  　|   |-- index.rst
  　|-- install
  　|-- index.rst <--- "xastro-it-automation Documentation" を記述

.. figure:: ../../images/ja_manual_design/title_in_index_rst_v_2_0.png
   :width: 5.84375in
   :height: 1.09375in
   :align: center
   :alt: title_in_index_rst

   各index.rst 内見出

index.rst 内構文
----------------
| indes.rst 内の記述方法について大章「インストール」内に配置した index.rst を例に挙げて説明します。
.. code-block:: bash
   
   ============ 
   インストール
   ============

   .. toctree::
   :maxdepth: 1

   getting_oase
   requirements
   installer/index
   container/index

| 以下に記述した内容が大章見出し (インストール) となります。
.. code-block:: bash
   
   ============ 
   インストール
   ============

.. figure:: ../../images/ja_manual_design/indexrst_syntax1_v2_0.png
   :width: 5.84375in
   :height: 1.09375in
   :align: center
   :alt: role_of_index

   大章まで表示


| 以下はどのレベルの見出しまで表示するかを指定しています。
.. code-block:: bash
   
   .. toctree::
   :maxdepth: 1

.. figure:: ../../images/ja_manual_design/toctree_lvl1.png
   :width: 5.84375in
   :height: 1.09375in
   :align: center
   :alt: role_of_index

   中章まで表示


.. code-block:: bash
   
   .. toctree::
   :maxdepth: 2

.. figure:: ../../images/ja_manual_design/toctree_lvl2.png
   :width: 5.84375in
   :height: 1.09375in
   :align: center
   :alt: role_of_index

   表示する見出しレベルを定義

| 以下にて配下にくる章が格納されているディレクトリを指定します。
.. code-block:: bash
   
   getting_oase
   requirements
   installer/index
   container/index


ドキュメント記述用 .rst ファイル
================================

構文 (見出)
-----------
.. code-block:: bash
   
   ======
   大見出
   ======
| |image1| 
|
|

.. code-block:: bash
   
   中見出
   ======
| |image2| 
|
|

.. code-block:: bash
   
   小見出1
   -------
| |image3| 
|
|

.. code-block:: bash
   
   小見出2
   ~~~~~~~
| |image3| 
|
|

.. code-block:: bash
   
   小見出3
   *******

| |image3| 
|

構文 (リスト)
-----------
.. code-block:: bash
   
   - リストa
   - リストb
- リストa
- リストb
|

.. code-block:: bash
   
   #. リストa
   #. リストb
#. リストa
#. リストb
|

構文 (強調)
-----------
.. code-block:: bash

   **強調されます**
**強調されます**
|

構文 (パラグラフ)
-----------------
.. code-block:: bash

   | パラグラフはじまり
   | つづきのパラグラ

   | 第二パラグラフ
| パラグラフはじまり
| つづきのパラグラフ

| 第二パラグラフ
|

|
.. code-block:: bash

   見出
     | 内容1
     | 内容2
見出
  | 内容1
  | 内容2

.. code-block:: bash

   #. | 番号付見出
      | 内容1
      | 内容2
#. | 番号付見出
   | 内容1
   | 内容2

構文 (画像差込)
---------------
.. code-block:: bash

   この下に画像が差し込まれます。

   .. figure:: ../../images/ja_manual_design/charg.png
      :width: 5in
      :height: 1in
      :align: center
      :alt: role_of_index

      index.rstの役割  <--- キャプション
この下に画像が差し込まれます。

.. figure:: ../../images/ja_manual_design/chart.png
   :width: 5in
   :height: 1in
   :align: center
   :alt: role_of_index

   index.rstの役割

|
.. code-block:: bash

   この下に画像が差し込まれます。

   .. image:: ../../images/ja_manual_design/chart.png
      :width: 5in
      :height: 1in
      :align: center
      :alt: role_of_index
この下に画像が差し込まれます。

.. image:: ../../images/ja_manual_design/chart.png
   :width: 5in
   :height: 1in
   :align: center
   :alt: role_of_index

|
.. code-block:: bash

   画像がここに→　|aa| 差し込まれます。

   .. |aa| image:: ../../images/ja_manual_design/sample_img_v2_0.png
      :width: 1.5in
      :height: 0.52in
      :alt: サンプルイメージ指定したパスにある画像が差し込まれます。

画像がここに→　|aa| 差し込まれます。

|
構文 (表差込)
-------------
.. code-block:: bash

   .. table:: 表組例1

      +----------+-------+---------+
      | 見出1    | 見出2 | 見出3   |
      |          |       |         |
      +==========+=======+=========+
      | 内容1    | 内容2 | 内容3   |
      +----------+-------+---------+
.. table:: 表組例1

   +----------+-------+---------+
   | 見出1    | 見出2 | 見出3   |
   |          |       |         |
   +==========+=======+=========+
   | 内容1    | 内容2 | 内容3   |
   +----------+-------+---------+
|
.. code-block:: bash

   .. csv-table:: .rst ファイル内構文2
      :header: 項目名1, 項目名2, 項目名3
      :widths: 10, 30, 30

      内容1, 内容2, 内容3

.. csv-table:: .rst ファイル内構文2
   :header: 項目名1, 項目名2, 項目名3
   :widths: 10, 30, 30

   内容1, 内容2, 内容3
|
.. warning:: | 表組1 では以下の記号は半角記号扱いとなります。
   | ※ (こめじるし),  ①などの〇付記号

|
構文 (ボタン)
-------------
.. code-block:: bash

   :guilabel:` アクション`
:guilabel:` アクション`

|
構文 (Note, Tip 等)
-------------
.. code-block:: bash

   .. note:: | 補足的な情報を示しています。
    | Note に記載されている内容は読み飛ばしても困ることは無いでしょう。
.. note:: | 補足的な情報を示しています。
   | Note に記載されている内容は読み飛ばしても困ることは無いでしょう。
|
.. code-block:: bash

   .. tip:: | 操作や作業におけるノウハウを示しています。
      | Tip に記載されている内容を読み飛ばした場合ユーザに混乱が生じる可能性があります。
.. tip:: | 操作や作業におけるノウハウを示しています。
   | Tip に記載されている内容を読み飛ばした場合ユーザに混乱が生じる可能性があります。
|
.. code-block:: bash

   .. warning:: | 操作上の注意点を示しています。
      | Warning に記載された内容はユーザが把握しておくほうが適切な情報です。
.. warning:: | 操作上の注意点を示しています。
   | Warning に記載された内容はユーザが把握しておくほうが適切な情報です。
|
.. code-block:: bash

   .. danger:: | 正常なサービスへ影響を与える可能性がある操作についての危険性を示しています。
      | Danger に記載された内容を知らない場合、大きな問題を引き起こす可能性があります。
.. danger:: | 正常なサービスへ影響を与える可能性がある操作についての危険性を示しています。
   | Danger に記載された内容を知らない場合、大きな問題を引き起こす可能性があります。


-  リスト
-  リスト２
    あさああああい 
-  LinuxはLinus
      Torvalds氏の米国およびその他の国における登録商標または商標です。

-  MariaDBは、MariaDB Foundationの登録商標または商標です。
| その他、本書に記載のシステム名、会社名、製品名は、各社の登録商標もしくは商標です。

.. |aa| image:: ../../images/ja_manual_design/chart.png
   :width: 1.5in
   :height: 0.52in
   :alt: サンプルイメージ
.. |image1| image:: ./manual_syntax/image1.png
   :width: 5.68735in
   :height: 0.56253in
.. |image2| image:: ./manual_syntax/image2.png
   :width: 5.68735in
   :height: 0.56253in
.. |image3| image:: ./manual_syntax/image3.png
   :width: 5.68735in
   :height: 0.56253in
.. |image6| image:: ./build_flow/image6.png
   :width: 5.68735in
   :height: 0.56253in
.. |image7| image:: ./manual_syntax/image7.png
   :width: 5.68735in
   :height: 0.56253in
.. |image8| image:: ./manual_syntax/image8.png
   :width: 5.68735in
   :height: 0.56253in
.. |image14| image:: ./build_flow/image14.png
   :width: 5.68735in
   :height: 0.56253in
.. |image15| image:: ./build_flow/image15.png
   :width: 5.60102in
   :height: 0.52416in
.. |image16| image:: ./build_flow/image16.png
   :width: 5.27072in
   :height: 0.49804in
.. |image17| image:: ./build_flow/image17.png
   :width: 5.54284in
   :height: 0.53672in
