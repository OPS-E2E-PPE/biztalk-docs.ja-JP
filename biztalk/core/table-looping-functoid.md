---
title: テーブル ループ Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140d173f9aa037174190d03bffad181423dfab5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291682"
---
# <a name="table-looping-functoid"></a>テーブル ループ Functoid
**テーブル ループ**functoid では、出力インスタンス メッセージの作成に使用する出力値のテーブルを作成することができます。 テーブル内のデータは、リンクおよび定数で構成できます。 最初の入力パラメーター、**テーブル ループ**functoid は、スコープを構成します。 または、何回レコードがループします。 2 番目のパラメーターの入力、**テーブル ループ**functoid によって列の数は、テーブル、および残りの入力は、任意の順序で、テーブルのセル値を定義します。 これらのプロパティの使用方法の詳細については、次を参照してください。 [Table-Driven ループの構成](../core/table-driven-looping-configuration.md)します。 参照してください[Table-Driven ループ例](../core/table-driven-looping-example.md)します。  
  
> [!NOTE]
>  **テーブル ループ**functoid に接続されているループ レコードに繰り返されます。 各反復処理内でテーブル ループ グリッドの各行は、複数の出力を生成するループに 1 回のループします。  
  
## <a name="see-also"></a>参照  
 [テーブル抽出 Functoid](../core/table-extractor-functoid.md)   
 [マップにテーブル抽出 Functoid およびテーブル ループを追加する方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)