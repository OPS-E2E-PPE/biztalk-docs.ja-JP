---
title: "テーブル ループ Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5e5f2967fb48bfe896c26246db1630266812f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="table-looping-functoid"></a>テーブル ループ Functoid
**テーブル ループ**functoid では、出力インスタンス メッセージの作成に使用する出力値のテーブルを作成することができます。 テーブル内のデータには、リンクおよび定数を含めることができます。 最初の入力パラメーター、**テーブル ループ**functoid は、スコープを構成するか、何回レコードがループします。 2 番目の入力パラメーター、**テーブル ループ**functoid では、テーブルに列の数を決定し、残りの入力が順不同でセル、テーブルの値を定義します。 これらのプロパティの使用の詳細については、次を参照してください。 [Table-Driven ループの構成](../core/table-driven-looping-configuration.md)です。 参照してください[Table-Driven ループ例](../core/table-driven-looping-example.md)です。  
  
> [!NOTE]
>  **テーブル ループ**に接続されているループ レコードに functoid が繰り返されます。 個々の繰り返し処理では、テーブル ループ グリッドの各行につき 1 回のループ処理が実行され、結果的に複数の出力ループが生成されます。  
  
## <a name="see-also"></a>参照  
 [テーブル抽出 Functoid](../core/table-extractor-functoid.md)   
 [テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)