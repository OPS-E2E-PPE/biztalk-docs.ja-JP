---
title: テーブル ドリブン ループの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb4efd2e067cf34113c6bb811207c21f8fd35c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291704"
---
# <a name="table-driven-looping-configuration"></a>テーブルドリブン ループの構成
マップのテーブルドリブン ループを構成するには、次の手順を実行します。  
  
- **テーブル ループ functoid をマップに追加します。** 1 つだけ必要があります**テーブル ループ**テーブルドリブン ループのインスタンスごとの functoid。 たとえば、BillTo および ShipTo 情報を派生させるテーブルドリブン ループを使用する場合必要があります 1 つだけ**テーブル ループ**マップに functoid。 ただし、BillTo および ShipTo 情報や、StoreName および StoreAddress 情報を派生させるテーブルドリブン ループを使用する場合を必要に応じて 2 つ**テーブル ループ**functoid をマップします。  
  
- **表示されているグリッド ページには、1 つ以上のテーブル抽出 functoid を追加します。** 多くの追加**テーブル抽出**ごとと functoid が必要な**テーブル ループ**functoid。 数**テーブル抽出**functoid は送信先スキーマのフィールドの数によって異なります。 のみがある場合など、 **AddressCode**で、送信元スキーマと CompanyName、アドレス、市区町村、状態、PostalCode、および AttentionName を送信先スキーマ、6 つ追加する必要があります**テーブル抽出**。表示されているグリッド ページに functoid。  
  
- **適切な入力では、テーブル ループ functoid を構成します。** 最初に、リンク、**テーブル ループ**functoid の入力インスタンス レコードまたは要素にします。 また、テーブル ループ Functoid を出力インスタンス メッセージの構造にもリンクします。 次を使用して、入力の構成、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 このプロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)します。 入力する入力の一覧は包括的な完全な構成に使用するデータは、このため、ある必要があります、**テーブル Functoid グリッド**プロパティ。 入力は、次のように定義する必要があります。  
  
  -   **最初の入力。** 最初の入力パラメーターは、入力インスタンス メッセージ レコード (またはフィールド) へのリンクです。 **テーブル ループ**functoid は、レコードまたはフィールドの各インスタンスに対して一度ループします。  
  
      > [!NOTE]
      >  この入力は必須です。  
  
  -   **2 番目の入力。** 2 番目の入力パラメーターは、ループ グリッドの列の数を定義します。 グリッドには、228 列まで格納できます。  
  
      > [!NOTE]
      >  この入力は必須です。  
  
  -   **残りの入力。** 残りの入力、**テーブル ループ**functoid のすべての可能な値に表示される一覧から成る、**テーブル Functoid グリッド**します。  
  
      > [!NOTE]
      >  リンクのラベル付けは、非常に便利です。 表示されるリンクのラベルを持たない、**テーブル Functoid グリッド**完全指定パス。  
  
       入力を構成する方法についてステップ バイ ステップの手順について、**テーブル ループ**functoid を参照してください[テーブル ループの追加とテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。 具体的には、手順 3. ~ 8. を参照してください。  
  
- **テーブル ループ functoid のテーブル Functoid グリッド プロパティを構成します。** 使用して、**テーブル Functoid グリッド**プロパティを開き、**テーブル ループ Functoid の構成**ループ グリッドのセルを構成する ダイアログ ボックス。  
  
   ループのグリッドを構成する方法の詳しい手順については、「[テーブル ループの追加とテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。 特に手順 9. と 10. が重要です。  
  
- **テーブル抽出 functoid を構成します。** 使用して、**入力パラメーター**プロパティを構成する、**テーブル抽出**functoid は次のように入力します。  
  
  - **最初の入力。** 最初の入力パラメーター、**テーブル抽出**functoid は、**テーブル ループ**functoid。  
  
  - **2 番目の入力。** 2 番目の入力パラメーターは、データを抽出する行の列を指定します。  
  
    ステップ バイ ステップの手順を構成する方法について、**テーブル抽出**functoid に関連付けられている、**テーブル ループ**functoid を参照してください[テーブル ループの追加とテーブル抽出する方法マップに Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。 特に手順 11 ～ 16 が重要です。  
  
## <a name="see-also"></a>参照  
 [テーブル ループ Functoid](../core/table-looping-functoid.md)   
 [テーブル抽出 Functoid](../core/table-extractor-functoid.md)   
 [テーブル ドリブン ループの例](../core/table-driven-looping-example.md)   
 [マップにテーブル抽出 Functoid およびテーブル ループを追加する方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)