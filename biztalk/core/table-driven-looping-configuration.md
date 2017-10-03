---
title: "テーブルドリブン ループの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Extractor functoids, configuring
- Table Extractor functoids
- Table Extractor functoids, adding to grid
- Table Looping functoids, about Table Looping functoids
- Table Looping functoids, configuring
- Table Extractor functoids, about Table Extractor functoids
- Table Looping functoids, adding to map
ms.assetid: ecc24d9b-ebc0-4559-9746-58e3b00c02ab
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563c7f26d2beb0eba33173507989cc85aaabda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="table-driven-looping-configuration"></a>テーブルドリブン ループの構成
マップのテーブルドリブン ループを構成するには、次の手順を実行します。  
  
-   **テーブル ループ functoid をマップに追加します。** 1 つだけで済みます**テーブル ループ**functoid ごと、テーブルドリブン ループのインスタンス。 たとえば、テーブルドリブン ループを BillTo および ShipTo 情報を派生させるために使用する場合必要があります 1 つだけ**テーブル ループ**functoid マップにします。 ただし、テーブルドリブン ループを BillTo および ShipTo 情報や、StoreName および StoreAddress 情報を派生させるために使用する場合必要があります 2**テーブル ループ**functoid をマップします。  
  
-   **表示されているグリッド ページに 1 つ以上のテーブル抽出 functoid を追加します。** いくつでも追加**テーブル抽出**ごとと functoid が必要な**テーブル ループ**functoid です。 数**テーブル抽出**functoid は送信先スキーマ内のフィールドの数によって異なります。 たとえば、しかない場合、 **AddressCode**で、送信元スキーマと CompanyName、アドレス、City、状態、PostalCode、および送信先スキーマの AttentionName、6 つ追加する必要があります**テーブル抽出**。functoid は、表示されているグリッド ページにします。  
  
-   **適切な入力で、テーブル ループ functoid を構成します。** 最初に、リンク、**テーブル ループ**functoid の入力インスタンス レコードまたは要素を送信します。 また、テーブル ループ Functoid を出力インスタンス メッセージの構造にもリンクします。 使用して、入力を次に、構成、**構成\<Functoid > Functoid**  ダイアログ ボックス。 このプロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。 これは、データを構成するのに使用するために、入力の一覧が包括的で完全なをする必要があります、**テーブル Functoid グリッド**プロパティです。 入力は、次のように定義する必要があります。  
  
    -   **最初の入力。** 最初の入力パラメーターは、入力インスタンス メッセージ レコード (またはフィールド) へのリンクです。 **テーブル ループ**functoid は、レコードまたはフィールドの各インスタンスに対して一度ループします。  
  
        > [!NOTE]
        >  この入力は必須です。  
  
    -   **2 番目の入力します。** 2 番目の入力パラメーターは、ループ グリッドの列の数を定義します。 グリッドには、228 列まで格納できます。  
  
        > [!NOTE]
        >  この入力は必須です。  
  
    -   **残りの入力。** 残りの入力、**テーブル ループ**functoid に含めることは有効な値のすべての一覧から成る、**テーブル Functoid グリッド**です。  
  
        > [!NOTE]
        >  リンクのラベル付けは、非常に便利です。 表示されるリンクのラベルを持たない、**テーブル Functoid グリッド**完全指定パス。  
  
         手順の入力を構成する方法については、**テーブル ループ**functoid を参照してください[テーブル ループの追加、およびテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。 具体的には、手順 3. ~ 8. を参照してください。  
  
-   **テーブル ループ functoid のテーブル Functoid グリッド プロパティを構成します。** 使用して、**テーブル Functoid グリッド**プロパティを開くには、 **[テーブル ループ Functoid**ループ グリッドのセルを構成する] ダイアログ ボックス。  
  
     ループのグリッドを構成する方法に関する詳細な手順については、次を参照してください。[テーブル ループの追加、およびテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。 特に手順 9. と 10. が重要です。  
  
-   **テーブル抽出 functoid を構成します。** 使用して、**入力パラメーター**プロパティを構成する、**テーブル抽出**functoid は次のように入力します。  
  
    -   **最初の入力。** 最初の入力パラメーター、**テーブル抽出**functoid は、**テーブル ループ**functoid です。  
  
    -   **2 番目の入力します。** 2 番目の入力パラメーターは、データを抽出する行の列を指定します。  
  
     手順を構成する方法については、**テーブル抽出**functoid に関連付けられている、**テーブル ループ**functoid を参照してください[テーブル ループの追加、およびテーブル抽出する方法マップに Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。 特に手順 11 ～ 16 が重要です。  
  
## <a name="see-also"></a>参照  
 [テーブル ループ Functoid](../core/table-looping-functoid.md)   
 [テーブル抽出 Functoid](../core/table-extractor-functoid.md)   
 [テーブルドリブン ループの例](../core/table-driven-looping-example.md)   
 [テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)