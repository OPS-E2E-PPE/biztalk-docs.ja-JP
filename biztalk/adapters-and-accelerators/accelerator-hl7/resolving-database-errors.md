---
title: データベース エラーの解決 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases
- errors, databases
ms.assetid: d7b1cc9f-3f3e-464a-8249-1fd03b2b4d76
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47a22877cf06f03f875138208281420e56963da9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206010"
---
# <a name="resolving-database-errors"></a>データベース エラーの解決
HL7 組織が発行する HL7 Access データベースでの Dataitem と TableValues は table_id と hl7_version によってリンクされている 2 つのテーブルです。 次のデータベース間のクエリは、一部のデータ アイテムがテーブルに示された値がない、table_id を参照することを示しています。  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 HL7 アクセスのデータベースは、列挙値がありませんが、クロス HL7 仕様では、手動で値をチェックして、スキーマでこれらの値を使用します。 このような状況に対処する 1 つの方法では、スキーマに列挙リストを追加します。 これを行うには、次を参照してください。[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)です。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)