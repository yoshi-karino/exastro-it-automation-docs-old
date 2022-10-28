===========================
Exastro OASE のシステム構成
===========================

| Exastro OASE は、要求に応じてシステムの構成をユーザが柔軟に選択できます。
| 下記にはその代表的な構成例を記載します。

オールインワン構成
==================

| 同一の基盤上に Exastro OASE のコンポーネントをすべて搭載する最もシンプルな構成例です。
| 構築作業や構成がシンプルな反面、SPoF(単一障害点)があるため Exastro OASE が稼働する基盤で障害が発生した場合、Exastro OASE が正常に動作しなくなる懸念があります。


.. figure:: /images/ja/introduction/deploy_all_in_one.png
   :scale: 80%
   :align: center

   オールインワン構成例

ハイアベイラビリティ構成
========================

| 複数の基盤上に Exastro OASE のコンポーネントを配置することで高い可用性や拡張性を実現する構成例です。
| オールインワンと比較して単一障害点を持たない分可用性や拡張性が上がる反面、構築作業や構成が複雑になります。

.. figure:: /images/ja/introduction/deploy_high_availability.png
   :scale: 80%
   :align: center

   ハイアベイラビリティ構成例