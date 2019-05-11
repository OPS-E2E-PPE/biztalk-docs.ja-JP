---
title: データベース エラーの解決 |Microsoft Docs
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
ms.openlocfilehash: 169dc680c4a49bd04dc61d0074d12d058b8d0a91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289927"
---
# <a name="resolving-database-errors"></a>データベース エラーの解決
HL7 組織を発行する HL7 Access データベース、Dataitem と TableValues、table_id と hl7_version によってリンクされている 2 つのテーブルとは。 次のデータベース間のクエリは、いくつかのデータ項目を表の値がない、table_id を参照することを示しています。  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 HL7 の Access データベースは、列挙値がありませんがある、する必要がありますクロス HL7 の仕様を手動で値をチェックを使用した場合これらの値、スキーマ内。 このような状況に対処する 1 つの方法では、スキーマに列挙リストを追加します。 これを行うを参照してください。[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)します。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Z オブジェクトを使用した HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)