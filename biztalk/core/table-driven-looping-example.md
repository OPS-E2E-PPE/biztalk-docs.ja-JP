---
title: テーブルドリブン ループの例 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids, code sample
- Table Looping functoids
- Table Extractor functoids
- Table Looping functoids, about Table Looping functoids
- Table Extractor functoids, about Table Extractor functoids
- code samples, Table Looping functoids
- Table Looping functoids, code sample
- code samples, Table Extractor functoids
ms.assetid: d890bdb1-12a6-4001-9748-737b1f2bab79
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6989ac7e64cf28784d08f26aaf9e7af3a166a28
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25974536"
---
# <a name="table-driven-looping-example"></a>テーブルドリブン ループの例
このセクションを使用して、マップ、 **テーブル ループ** と **テーブル抽出** functoid です。 詳細についてを選択すると、配置、リンク、および、functoid の構成を参照してください[テーブル ループの追加、およびテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。  
  
 出荷先住所と請求先住所を別々に掲載するドキュメントで使用される、住所の一覧を例として説明します。 住所は、次のコードのように表されます。  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.Addresses">  
    <Address>  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address>  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 次のコードは出力形式の例を示しています。ここでは、住所が複製され、各住所に属性が設定されています。  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.POAddresses">  
    <Address Type="ShipTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City><State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="ShipTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 `The following figure shows a map using the`  **テーブル** **ループ**  `functoid and`  **テーブル** **抽出**  `functoids to generate the desired output instance message.`  
  
 ![テーブル ループとテーブル抽出 functoid マップ](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")  
テーブル ループ Functoid とテーブル抽出 Functoid  
  
 注意して、 **テーブル ループ** functoid が入力と出力の両方のスキーマのレコード レベルの要素にリンクします。 リンクによって、囲み構造が作成され、レコード内に要素が作成されます。 またことがあることを確認 **テーブル抽出** functoid の出力スキーマ内の各フィールドです。  
  
 入力スキーマのレコードへのリンクは、最初のパラメーター、**構成\<Functoid\> Functoid** ダイアログ ボックス。  
  
 2 番目のパラメーターは、functoid のグリッド テーブルの列の数: 1 列ごとのアドレスの種類、名前、番地、市区町村、状態、および郵便番号。 2 つ目のパラメーターの後には、グリッド テーブルに表示されるすべての値の一覧が示されています。 一覧には、住所のフィールドへのリンクと共に、住所の種類 ("ShipTo" および "BillTo") に使用する文字列の定数が含まれます。 住所のフィールドへのリンクに名前があることに注意してください。 マップ内のリンクに名前を付けると、テーブルの構築がわかりやすくなります。 完全なパスを表示するそれ以外の場合、 **[テーブル ループ Functoid** ] ダイアログ ボックス。  
  
 構成した後、 **テーブル ループ** functoid を使用してテーブルを作成することができます、 **[テーブル ループ Functoid** ] ダイアログ ボックス。 省略記号ボタンをクリックすると、ダイアログ ボックスが表示されます (**...**) に関連付けられたボタン、 **テーブル ループ グリッド** プロパティに、 **プロパティ** ウィンドウです。  
  
 指定されている 6 つの列があることに注意してください、 **テーブル ループ Functoid** ダイアログ: 出力スキーマのフィールドごとに 1 つの列です。 ドロップダウン リストは、3 番目以降のパラメーターで指定されたフィールドの値を示しています、 **テーブル ループ Functoid** ダイアログ。 テーブルには、2 行 (出力スキーマの各種類のレコード) あります。 2 行存在するので、このマップは、入力レコードごとに 2 つのレコードを作成します。 4 行存在する場合は、入力レコードごとに 4 つの出力レコードが作成されます。  
  
 として、 **テーブル ループ** functoid は、各レコードは、これは、レコードの値を持つテーブルを入力しに一度に 1 つの行を送信、 **テーブル抽出** functoid です。 **テーブル抽出** functoid のテーブルの行から 1 つの値を抽出各と出力インスタンス メッセージにリンクされているフィールドを渡します。  
  
## <a name="see-also"></a>参照  
 [テーブル ループ Functoid](../core/table-looping-functoid.md)   
 [テーブル抽出 Functoid](../core/table-extractor-functoid.md)   
 [テーブルドリブン ループの構成](../core/table-driven-looping-configuration.md)   
 [テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)