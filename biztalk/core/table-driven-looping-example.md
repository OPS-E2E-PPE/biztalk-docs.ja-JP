---
title: テーブル ドリブン ループの例 |Microsoft Docs
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
ms.openlocfilehash: 505738960cb47930c210398dd76ffe394fe71637
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291663"
---
# <a name="table-driven-looping-example"></a>テーブル ドリブン ループの例
マップを使用して、簡単な説明、**テーブル ループ**と**テーブル抽出**functoid。 詳細についてを選択すると、配置することで、リンク、および、functoid の構成を参照してください[テーブル ループの追加とテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。  
  
 別の送付先と請求先のアドレスを必要とするドキュメントで使用する必要があるアドレスの一覧とします。 次のように、アドレスがあります。  
  
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
  
 1 つの形式の出力がかかる場合があります、アドレスの重複が属性でマークして、次のコードになります。  
  
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
  
 `The following figure shows a map using the`  **テーブル****ループ**`functoid and`**テーブル****エクス トラクター**   `functoids to generate the desired output instance message.`  
  
 ![テーブル ループとテーブル抽出 functoid をマップ](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")  
Functoid およびテーブル抽出 Functoid  
  
 なお、**テーブル ループ**functoid が入力と出力の両方のスキーマのレコード レベルの要素にリンクします。 リンクは、外側の構造の作成と、そのため、レコード内の要素の作成を設定します。 1 つまた**テーブル抽出**functoid の出力スキーマのフィールドごとにします。  
  
 入力スキーマのレコードへのリンクは、最初のパラメーターで、**構成\<Functoid\> Functoid** ダイアログ ボックス。  
  
 2 番目のパラメーターは、functoid のグリッド テーブルの列の数: 1 つの列それぞれのアドレスの種類、名前、番地、市区町村、状態、および郵便番号。 次の 2 番目のパラメーターは、すべてのグリッド テーブルに表示される値の一覧です。 アドレスのフィールドへのリンクと共に、アドレスの種類 ("ShipTo"、"BillTo") の文字列定数が含まれます。 住所のフィールドへのリンクが名前を持つことに注意してください。 マップ内のリンクの名前を付けるには、テーブルの構築が簡略化します。 完全なパスを表示する場合は、**テーブル ループ Functoid の構成** ダイアログ ボックス。  
  
 構成した後、**テーブル ループ**functoid を使用してテーブルを構築することができます、**テーブル ループ Functoid の構成** ダイアログ ボックス。 省略記号をクリックすると、ダイアログ ボックスが表示されます (**.**) ボタンに関連付けられている、**テーブル ループ グリッド**プロパティ、**プロパティ**ウィンドウ。  
  
 指定されている 6 つの列があることに注意してください、**テーブル ループ Functoid の構成**ダイアログ: 出力スキーマのフィールドごとに 1 つの列。 ドロップダウン リストで 3 つ目以降のパラメーターで指定されたフィールドの値を示しています、**テーブル ループ Functoid の構成**ダイアログ。 テーブルには、出力スキーマのレコードの種類ごとに 1 つずつ、2 つの行があります。 2 つの行があるため、このマップには、入力レコードごとに 2 つのレコードが生成されます。 4 つの行があった場合は、各入力レコードの 4 つの出力レコードがあります。  
  
 として、**テーブル ループ**functoid が各レコードをレコードの値を持つテーブルに格納し、一度に 1 つの行を送信、**テーブル抽出**functoid。 **テーブル抽出**functoid のテーブルの行から 1 つの値を抽出各と、出力インスタンス メッセージでリンクされているフィールドに渡します。  
  
## <a name="see-also"></a>参照  
 [テーブル ループ Functoid](../core/table-looping-functoid.md)   
 [テーブル抽出 Functoid](../core/table-extractor-functoid.md)   
 [テーブル ドリブン ループの構成](../core/table-driven-looping-configuration.md)   
 [マップにテーブル抽出 Functoid およびテーブル ループを追加する方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)