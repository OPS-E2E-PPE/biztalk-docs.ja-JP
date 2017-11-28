---
title: "データベース エラーの解決 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases
- errors, databases
ms.assetid: d7b1cc9f-3f3e-464a-8249-1fd03b2b4d76
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47a22877cf06f03f875138208281420e56963da9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-database-errors"></a><span data-ttu-id="04f44-102">データベース エラーの解決</span><span class="sxs-lookup"><span data-stu-id="04f44-102">Resolving Database Errors</span></span>
<span data-ttu-id="04f44-103">HL7 組織が発行する HL7 Access データベースでの Dataitem と TableValues は table_id と hl7_version によってリンクされている 2 つのテーブルです。</span><span class="sxs-lookup"><span data-stu-id="04f44-103">In the HL7 Access database that the HL7 organization publishes, DataItems and TableValues are two tables linked by table_id and hl7_version.</span></span> <span data-ttu-id="04f44-104">次のデータベース間のクエリは、一部のデータ アイテムがテーブルに示された値がない、table_id を参照することを示しています。</span><span class="sxs-lookup"><span data-stu-id="04f44-104">The following database cross-query shows that some data items refer to a table_id, which has no values listed in the table:</span></span>  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 <span data-ttu-id="04f44-105">HL7 アクセスのデータベースは、列挙値がありませんが、クロス HL7 仕様では、手動で値をチェックして、スキーマでこれらの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="04f44-105">If the HL7 Access database has missing enumeration values, you must cross check the values manually with the HL7 specifications and use those values in your schema.</span></span> <span data-ttu-id="04f44-106">このような状況に対処する 1 つの方法では、スキーマに列挙リストを追加します。</span><span class="sxs-lookup"><span data-stu-id="04f44-106">One way to deal with this situation is to add an enumeration list to the schema.</span></span> <span data-ttu-id="04f44-107">これを行うには、次を参照してください。[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)です。</span><span class="sxs-lookup"><span data-stu-id="04f44-107">To do so, see [Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f44-108">参照</span><span class="sxs-lookup"><span data-stu-id="04f44-108">See Also</span></span>  
 <span data-ttu-id="04f44-109">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="04f44-109">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 [<span data-ttu-id="04f44-110">Z オブジェクトと HL7 2.X スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="04f44-110">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)