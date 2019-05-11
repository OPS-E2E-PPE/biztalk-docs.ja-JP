---
title: SQL アダプターを使用して SQL Server で複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95c7863666317b42fa32b04073244915eae6d7dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367979"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a><span data-ttu-id="db995-102">SQL アダプターを使用して SQL Server で複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="db995-102">Run composite operations in SQL Server  using the SQL adapter</span></span>
<span data-ttu-id="db995-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアントが SQL Server データベースでの複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="db995-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables adapter clients to perform composite operations on the SQL Server database.</span></span> <span data-ttu-id="db995-104">複合操作では、および任意の順序で、次の操作の任意の数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="db995-104">A composite operation can include any number of the following operations, and in any order:</span></span>  
  
- <span data-ttu-id="db995-105">テーブルおよびビューに対する Insert、Update、および Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="db995-105">The Insert, Update, and Delete operations on the tables and views.</span></span>  
  
- <span data-ttu-id="db995-106">アダプターでの操作として表示されるストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="db995-106">Stored procedures that are surfaced as operations in the adapter.</span></span>  
  
  <span data-ttu-id="db995-107">複合操作に含まれる操作*する必要があります*テーブルとビューでは、1 つのデータベースのみを対象します。</span><span class="sxs-lookup"><span data-stu-id="db995-107">The operations in a composite operation *must* target tables and views only in a single database.</span></span>  
  
  <span data-ttu-id="db995-108">詳細については。</span><span class="sxs-lookup"><span data-stu-id="db995-108">For information about:</span></span>  
  
- <span data-ttu-id="db995-109">複合操作を実行する方法[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL Server を使用して BizTalk Server での複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="db995-109">How to perform composite operations in [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on SQL Server Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="db995-110">複合操作のスキーマのメッセージを参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="db995-110">Message schemas for the composite operation, see [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db995-111">"N"の数を返す複合操作での操作がある接続の数に設定し、"n+1"結果は複合操作が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db995-111">If there are “n” number of operations in a composite operation that return a result set then “n+1” number of connections are required for the composite operation to be executed.</span></span> <span data-ttu-id="db995-112">そのため、することが必要に指定された値、 **MaxConnectionPoolSize**プロパティのバインドは、n+1 以上。</span><span class="sxs-lookup"><span data-stu-id="db995-112">Therefore, you must ensure that the value specified for the **MaxConnectionPoolSize** binding property is n+1 or greater.</span></span> <span data-ttu-id="db995-113">詳細については、 **MaxConnectionPoolSize**プロパティ、バインドを参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="db995-113">For more information about the **MaxConnectionPoolSize** binding property, see [Read about BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db995-114">参照</span><span class="sxs-lookup"><span data-stu-id="db995-114">See Also</span></span>  
 <span data-ttu-id="db995-115">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="db995-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>