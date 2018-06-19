---
title: SQL アダプタを使用して SQL Server で複合操作を実行 |Microsoft ドキュメント
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
ms.openlocfilehash: c36a1ff6e4b2c7d4d56855ce1531f99cd490a2a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223330"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a><span data-ttu-id="b223e-102">SQL アダプタを使用して SQL Server での複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b223e-102">Run composite operations in SQL Server  using the SQL adapter</span></span>
<span data-ttu-id="b223e-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアントが、SQL Server データベースでの複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b223e-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables adapter clients to perform composite operations on the SQL Server database.</span></span> <span data-ttu-id="b223e-104">複合操作は、次の操作、および任意の順序で任意の数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b223e-104">A composite operation can include any number of the following operations, and in any order:</span></span>  
  
-   <span data-ttu-id="b223e-105">テーブルおよびビューに対する Insert、Update、および Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="b223e-105">The Insert, Update, and Delete operations on the tables and views.</span></span>  
  
-   <span data-ttu-id="b223e-106">アダプターでの操作として表示されたストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="b223e-106">Stored procedures that are surfaced as operations in the adapter.</span></span>  
  
 <span data-ttu-id="b223e-107">複合操作の操作は、*必要があります*テーブルとビューを 1 つのデータベースでのみを対象します。</span><span class="sxs-lookup"><span data-stu-id="b223e-107">The operations in a composite operation *must* target tables and views only in a single database.</span></span>  
  
 <span data-ttu-id="b223e-108">詳細については。</span><span class="sxs-lookup"><span data-stu-id="b223e-108">For information about:</span></span>  
  
-   <span data-ttu-id="b223e-109">複合操作を実行する方法[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL Server を使用して BizTalk Server での複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="b223e-109">How to perform composite operations in [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on SQL Server Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="b223e-110">メッセージ複合操作のスキーマを参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="b223e-110">Message schemas for the composite operation, see [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b223e-111">"N"を返す操作で複合操作ではさまざまな接続の数に設定し、"n+1"結果は複合操作が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b223e-111">If there are “n” number of operations in a composite operation that return a result set then “n+1” number of connections are required for the composite operation to be executed.</span></span> <span data-ttu-id="b223e-112">したがって、ことを確認用に指定された値、 **MaxConnectionPoolSize** n+1 プロパティのバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="b223e-112">Therefore, you must ensure that the value specified for the **MaxConnectionPoolSize** binding property is n+1 or greater.</span></span> <span data-ttu-id="b223e-113">詳細については、 **MaxConnectionPoolSize**バインディング プロパティを参照してください[BizTalk Adapter for SQL Server のアダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="b223e-113">For more information about the **MaxConnectionPoolSize** binding property, see [Read about BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b223e-114">参照</span><span class="sxs-lookup"><span data-stu-id="b223e-114">See Also</span></span>  
 <span data-ttu-id="b223e-115">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="b223e-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>